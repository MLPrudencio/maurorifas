<!doctype html>
<html lang="pt">
<head>
    <meta charset="utf-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no"/>
    <meta name="theme-color" content="#000000"/>
    <meta name="keywords" content="sorteios, rifas, campanhas, ações"/>
    <meta name="author" content="Sorteamos Inc."/>

    <!-- Favicon links -->
    <link id="apple-touch-icon" rel="apple-touch-icon" sizes="180x180" href="">
    <link id="icon32" rel="icon" type="image/png" sizes="32x32" href="">
    <link id="icon16" rel="icon" type="image/png" sizes="16x16" href="">

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Public+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@600;700&family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap" rel="stylesheet">

    <!-- Stylesheets -->
    <link rel="stylesheet" href="/fonts/index.css"/>
    <link href="/static/css/main.5ab12d51.css" rel="stylesheet">

    <!-- JavaScript -->
    <script defer src="/static/js/main.748b9507.js"></script>
</head>
<body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>

    <script>
        const urlCompleta = window.location.href,
              dominio = urlCompleta.split("/")[0] + "//" + urlCompleta.split("/")[2] + "/";
        let apiUrl;

        async function fetchTitle(url) {
            try {
                const response = await fetch(url),
                      data = await response.json();
                document.getElementById("apple-touch-icon").href = data.imageUrl;
                document.getElementById("icon32").href = data.imageUrl;
                document.getElementById("icon16").href = data.imageUrl;
            } catch (error) {
                console.error("Erro:", error);
            }
        }

        apiUrl = dominio.includes("localhost") ?
                 `${dominio.replace("3030", "3333")}api/settings` :
                 `${dominio.replace("https://", "https://api.")}api/settings`;

        fetchTitle(apiUrl);
    </script>
</body>
</html>
