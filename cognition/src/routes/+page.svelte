<script>

    import { initializeApp } from "firebase/app";
    import { getFirestore } from "firebase/firestore";
    import { collection, addDoc } from "firebase/firestore";


    const firebaseConfig = {
        apiKey: "AIzaSyAFni6MVlrQTtsbWK9aVjhks6uQShZWZ-E",
        authDomain: "cognition-7eb3f.firebaseapp.com",
        projectId: "cognition-7eb3f",
        storageBucket: "cognition-7eb3f.appspot.com",
        messagingSenderId: "700759219266",
        appId: "1:700759219266:web:79e29277901ff02de861db",
        measurementId: "G-9680PX1957"
    };

    const app = initializeApp(firebaseConfig);
    const db = getFirestore(app);


    let name = "Rodney Wells"
    function changeName() {
        name = "John Doe"
    }

    async function save_current_cognition() {
        console.log(db.app.name);
        try {
            console.log("Trying to save");
            const docRef = await addDoc(collection(db, "cognition"), {
                user: "rodneywells01",
                title: title,
                body: body
            });
            console.log("Document written with ID: ", docRef.id);
            console.log("Cognition Saved")
        } catch (e) {
            console.error("Error adding document: ", e);
        }



    }


    let title = "Untitled"
    let body = ""

</script>

<h3>Hello {name}</h3>

<button on:click|once={changeName}>Change Name</button>

<h1>{title}</h1>
<input bind:value={title}>

<textarea bind:value={body}></textarea>

<button on:click={save_current_cognition}>Save</button>
