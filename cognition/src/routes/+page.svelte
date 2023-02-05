<script>
    let name = "Rodney Wells"
    function changeName() {
        name = "John Doe"
    }

    function save_current_cognition() {
        console.log("Saving cognition")
        console.log("Title: " + title)
        console.log("Body: " + body)
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
