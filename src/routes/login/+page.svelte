<script>
    let hello = "";

    fetch('http://127.0.0.1:8000/')
        .then(response => response.json())
        .then(data => {
            hello = data.message;
        })
        .catch(error => {
            console.error('Error:', error);
        });
</script>

<h1>{hello}</h1>
