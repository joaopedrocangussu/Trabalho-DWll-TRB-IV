# Trabalho-DWll-TRB-IV Q1

<?php
        for ($i = 1; $i <= 100; $i++) {
            if ($i % 3 == 0 && $i % 5 != 0) {
                echo $i . " ";
            }
        }
        ?>

        <?php
        for ($i = 1; $i <= 100; $i++) {
            if ($i % 5 == 0 && $i % 3 != 0) {
                echo $i . " ";
            }
        }
        ?>

# Trabalho-DWll-TRB-IV Q2
<?php

echo "Informe um número: ";
$numero = readline();

if ($numero % 2 == 0) {
    echo "O número $numero é par!";
} else {
    echo "O número $numero é ímpar!";
}
?>


# Trabalho-DWll-TRB-IV Q3
<!DOCTYPE html>
<html>
<head>
    <title>Contador de Caracteres</title>
</head>
<body>
    <form method="post">
        <label for="texto">Digite uma palavra ou texto:</label>
        <input type="text" name="texto" id="texto">
        <button type="submit">Contar</button>
    </form>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $input_text = $_POST["texto"];
        $num_caracteres = strlen($input_text);
        echo "<p>A quantidade de caracteres digitados é: $num_caracteres</p>";
    }
    ?>
</body>
</html>


# Trabalho-DWll-TRB-IV Q4
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Simples</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">

</head>
<body>
    <div class="container">
        <h1>Calculadora Simples</h1>
        <form action="" method="post">
            <label for="num1">Número 1:</label>
            <input type="number" name="num1" id="num1" required>

            <label for="num2">Número 2:</label>
            <input type="number" name="num2" id="num2">

            <label for="operation">Operação:</label>
            <select name="operation" id="operation" required>
                <option value="adição">Soma</option>
                <option value="subtração">Subtração</option>
                <option value="multi">Multiplicação</option>
                <option value="divição">Divisão</option>
                <option value="raiz">Raiz Quadrada</option>
            </select>

            <input type="submit" value="Calcular">
        </form>

        <?php
        if ($_SERVER["REQUEST_METHOD"] == "POST") {
            $num1 = $_POST["num1"];
            $num2 = $_POST["num2"];
            $operation = $_POST["operation"];
            $result = "";

            switch ($operation) {
                case "adição":
                    $result = $num1 + $num2;
                    echo "<div class='result'>Resultado: $num1 + $num2 = $result</div>";
                    break;
                case "subtração":
                    $result = $num1 - $num2;
                    echo "<div class='result'>Resultado: $num1 - $num2 = $result</div>";
                    break;
                case "multi":
                    $result = $num1 * $num2;
                    echo "<div class='result'>Resultado: $num1 * $num2 = $result</div>";
                    break;
                case "divição":
                    if ($num2 == 0) {
                        echo "<div class='result'>Erro: Divisão por zero não é permitida.</div>";
                    } else {
                        $result = $num1 / $num2;
                        echo "<div class='result'>Resultado: $num1 / $num2 = $result</div>";
                    }
                    break;
                case "raiz":
                    $result = sqrt($num1);
                    echo "<div class='result'>Resultado: √$num1 = $result</div>";
                    break;
                default:
                    echo "<div class='result'>Operação inválida.</div>";
                    break;
            }
        }
        ?>
    </div>
</body>
</html>



# Trabalho-DWll-TRB-IV Q5

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contato</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    
</head>
<body>
    <div class="container">
        <h1>Contato</h1>
        <form id="contactForm" method="post" action="">
            <label for="nome">Nome:</label>
            <input type="text" id="nome" name="nome" required>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>

            <label for="mensagem">Mensagem:</label>
            <textarea id="mensagem" name="mensagem" rows="4" required></textarea>

            <label for="motivo">Motivo do Contato:</label>
            <select id="motivo" name="motivo" required>
                <option value="" disabled selected>Selecione um motivo</option>
                <option value="duvida">Dúvida</option>
                <option value="feedback">Feedback</option>
                <option value="problema">Problema</option>
                <option value="outro">Outro</option>
            </select>

            <button type="submit">Enviar</button>
        </form>

        <?php
        if ($_SERVER["REQUEST_METHOD"] == "POST") {
            $nome = $_POST["nome"];
            $email = $_POST["email"];
            $mensagem = $_POST["mensagem"];
            $motivo = $_POST["motivo"];

            echo "<div class='result'>";
            echo "<h2>Dados Recebidos:</h2>";
            echo "<p><strong>Nome:</strong> $nome</p>";
            echo "<p><strong>Email:</strong> $email</p>";
            echo "<p><strong>Mensagem:</strong> $mensagem</p>";
            echo "<p><strong>Motivo:</strong> $motivo</p>";
            echo "</div>";
        }
        ?>

    </div>
</body>
</html>


# Trabalho-DWll-TRB-IV Q6


<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IGNIS</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="css/style.css">

</head>
<body class="dark-mode">
    <nav class="navbar navbar-expand-lg navbar-dark-mode">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">
                <img src="/QUESTÃO6/css/OIP-removebg-preview.png" alt="Logo" width="60" height="50" class="d-inline-block align-text-top">
            </a>
            <a id="LOGO" class="navbar-brand" href="#">IGNIS</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link active" aria-current="page" href="#">HOME</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">MENSAGENS</a>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">CURTIDAS</a>
                        <ul class="dropdown-menu dark-mode">
                            <li><a class="dropdown-item" href="#">Favoritados</a></li>
                            <li><a class="dropdown-item" href="#">Like</a></li>
                            <li><hr class="dropdown-divider"></li>
                            <li><a class="dropdown-item" href="#">Assistir mais tarde</a></li>
                        </ul>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link disabled" aria-disabled="true">DEGUIMAR</a>
                    </li>
                </ul>
                <form class="d-flex" role="search">
                    <input class="form-control me-2 dark-mode" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
                    <button class="btn btn-outline-success dark-mode" type="submit">Pesquisar</button>
                </form>
            </div>
        </div>
    </nav>
    <div class="container mt-5 dark-mode">
        <h2>Postagens</h2>
        <form id="postForm" method="post" action="">
            <input type="hidden" name="action" value="create">
            <div class="mb-3">
                <label for="postContent" class="form-label">Escreva sua postagem:</label>
                <textarea class="form-control dark-mode" id="postContent" name="texto" rows="3" required></textarea>
            </div>
            <button type="submit" class="btn btn-primary dark-mode">Postar</button>
        </form>
        <div id="postContainer" class="mt-3">
            <?php foreach ($publicacoes as $publicacao): ?>
                <div class="card mb-3 dark-mode">
                    <div class="card-body">
                        <p class="card-text"><?= htmlspecialchars($publicacao['texto']) ?></p>
                        <button class="btn btn-sm btn-outline-primary like-button" data-id="<?= $publicacao['id'] ?>">
                            <?= $publicacao['curtida'] ? 'Curtido' : 'Curtir' ?>
                        </button>
                        <button class="btn btn-sm btn-outline-danger delete-button" data-id="<?= $publicacao['id'] ?>">Excluir</button>
                    </div>
                </div>
            <?php endforeach; ?>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
    <script src="QUESTÃO6/js/script.js"> </script>
</body>
</html>
