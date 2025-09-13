<!DOCTYPE html>
<html>
<head>
    <title>Extract Data from XML</title>
</head>
<body>
    <h1>Data from XML</h1>
    <div id="output"></div>

    <script>
        // Sample XML data
        const xmlData = `
            <books>
                <book>
                    <title>Book Title 1</title>
                    <author>Author 1</author>
                </book>
                <book>
                    <title>Book Title 2</title>
                    <author>Author 2</author>
                </book>
            </books>
        `;

        // Parse the XML
        const parser = new DOMParser();
        const xmlDoc = parser.parseFromString(xmlData, "text/xml");

        // Extract data
        const books = xmlDoc.getElementsByTagName("book");
        let output = "<ul>";
        for (let i = 0; i < books.length; i++) {
            const title = books[i].getElementsByTagName("title")[0].textContent;
            const author = books[i].getElementsByTagName("author")[0].textContent;
            output += `<li><strong>${title}</strong> by ${author}</li>`;
        }
        output += "</ul>";

        // Display data
        document.getElementById("output").innerHTML = output;
    </script>
</body>
</html># My-Start-Application
