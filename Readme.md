![Alt text](imgs/0.jpeg)


Pré Requisitos:

PHP
Composer https://getcomposer.org/
Editor de Texto de sua preferência

1) Autoload com classmap:

```
{
    "name": "paulo-correia/Autoload_Composer",
    "description": "Autload com o Composer - Classmap",
    "minimum-stability": "stable",
    "license": "MIT",
    "authors": [
           {
            "name": "Paulo Correia",
            "role": "Developer",
            "homepage": "https://github.com/paulo-correia"
        }
    ],
    "config": {
        "vendor-dir": "vendor"
    },
    "autoload" : {
     "classmap" : [
        "Testing" ]
      }
}

```

Onde o "Testing" é a pasta onde vão estar as suas classes, esta pasta fica na "raiz" do seu projeto.

2) Autoload com Namespace

```
{
    "name": "paulo-correia/Autoload_Composer",
    "description": "Autload com o Composer - Namespace",
    "minimum-stability": "stable",
    "license": "MIT",
    "authors": [
           {
            "name": "Paulo Correia",
            "role": "Developer",
            "homepage": "https://github.com/paulo-correia"
        }
    ],
    "config": {
        "vendor-dir": "vendor"
    },
    "autoload": {
        "psr-4": {
          "Testing\\":"src/"    }
  }
}
```

Onde o "Testing" é o Namespace e "src" é a pasta onde vão estar as suas classes, esta pasta fica na "raiz" do seu projeto.

3) Comando do composer para "criar" o autoload (Escolha uma forma [Namespace/Classmap] e salve um dos códigos com o nome de composer.json)

```
composer install
```

4) Index.php que vai carregar o autoload (classmap)

```
<?php

require "vendor/autoload.php";

$t = new Test();

var_dump ($t->test());

```

5) Index.php que vai carregar o autoload (namespace)

```
<?php

require "vendor/autoload.php";

use Testing\Test;

$t = new Test();

var_dump ($t->test());
```

6) Classe test.php (classmap) -- Aqui o arquivo pode ter qualquer nome e tem que ficar dentro da pasta Testing (Testing/test.php)

```
<?php

class Test {

        public function test() {
                return "test";
        }

}

```

7) Classe Test.php (namespace) -- O Arquivo tem que ser o nome da classe e tem que ficar dentro da pasta src (src/Test.php)

```
<?php

namespace Testing;

class Test {

        public function test() {
                return "test";
        }

}
```


