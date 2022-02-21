Data e Hora
-----------

```php
date_default_timezone_set("America/Sao_Paulo");
echo date("d/m/Y h:i:s"); // 28/04/2017 13:45:09
$hora = date("h");
```

Arquivos Texto
--------------

Leitura

```php
// leitura de arquivo
$filename = "c:\\data\\info.txt";
$file = fopen($filename, "r");
$content = fread($file, filesize($filename));
fclose($file);
```

Gravação

```php
// gravação no arquivo
$text = "test";
$filename = "c:\\data\\info.txt";
$file = fopen($filename, "a+");
fwrite($file, $text);
fclose($file);
```

Modos de abertura de arquivo

```php
"r"   // somente leitura, ponteiro no início do arquivo 
"r+"  // leitura e escrita, ponteiro no início do arquivo
"w"   // somente escrita, ponteiro no início do arquivo
      // reduz o tamanho do arquivo para 0 
      // se o arquivo não existe, tenta criá-lo
"w+"  // leitura e escrita, ponteiro no início do arquivo
      // reduz  o tamanho do arquivo para 0
      // se o arquivo não existe, tenta criá-lo
"a"   // somente escrita, ponteiro no final do arquivo
      // se o arquivo não existe, tenta criá-lo
"a+"  // leitura e escrita, ponteiro no final do arquivo
      // se o arquivo não existe, tenta criá-lo
"x"   // cria um arquivo e abre somente para escrita, ponteiro no início do arquivo
      // se o arquivo já existir, retorna erro
"x+"  // cria um arquivo e abre para leitura escrita, ponteiro no início do arquivo
      // se o arquivo já existir, retorna erro
```

Post e Get
----------

Array associativo que recupera dados passados via POST ou via GET

```php
echo $_POST["name"];
echo $_GET["name"];
```

JSON
----

```php
$array = array(
  "titulo" => "Titanic",
  "ano" => 2017,
  "horarios" => array ("16:00", "19:00", "20:00")
)
$jsonStr = json_encode($array);
$jsonArray = json_decode($jsonStr);
```

Criptografia
------------

```php
<?php

    $expressao = "Batatinha quando nasce";

    echo sha1($expressao), PHP_EOL;
    echo md5($expressao), PHP_EOL;
    echo base64_encode($expressao), PHP_EOL;
    echo base64_decode(base64_encode($expressao)), PHP_EOL;
?>
```

Cookies
-------

```php
<?php
    setcookie("chave", "valor", time()+3600);  // cria valor para expirar em 1 hora 
    setcookie("chave", "valor2");              // altera valor
    //setcookie("chave", null, -1);              // deleta valor
    echo $_COOKIE["chave"];                    // acessa valor
?>
```