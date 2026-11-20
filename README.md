
<!DOCTYPE html>
<html>
<head>
    <title>Async Programming</title>
    <link rel="stylesheet" href="style.css">
    <style>

body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    text-align: center;
    margin-top: 100px;
}

.container {
    background-color: white;
    width: 400px;
    margin: auto;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 0 10px gray;
}

h1 {
    color: #333;
}

button {
    background-color: blue;
    color: white;
    padding: 12px 25px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    background-color: darkblue;
}

#status {
    color: orange;
    margin-top: 20px;
}

#result {
    color: green;
    font-size: 18px;
    margin-top: 15px;
}

    </style>
</head>
<body>

    <div class="container">
        <h1>Server Data Fetching</h1>

        <p>Click the button to fetch data from server.</p>

        <button onclick="fetchData()">Fetch Data</button>

        <h3 id="status"></h3>

        <div id="result"></div>
    </div>
    <script>

function fetchData() {

    document.getElementById("status").innerHTML =
        "Fetching data from server...";

    document.getElementById("result").innerHTML = "";
    let promise = new Promise((resolve, reject) => {
        setTimeout(() => {

            let data = {
                name: "Uday",
                age: 20,
                course: "Computer Science"
            };

            resolve(data);

        }, 2000);

    });
    promise.then((data) => {

        document.getElementById("status").innerHTML =
            "Data fetched successfully!";

        document.getElementById("result").innerHTML =
            "Name: " + data.name + "<br>" +
            "Age: " + data.age + "<br>" +
            "Course: " + data.course;

    }).catch((error) => {

        document.getElementById("status").innerHTML =
            "Error: " + error;

    });

}

    </script>

</body>
</html>
