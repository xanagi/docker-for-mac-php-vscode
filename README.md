# vagrant-docker-php-vscode

## Description

This is a sample project that demonstrates debugging of a PHP application that runs on Docker for Mac.

## Requirement
- [Visual Studio Code](https://code.visualstudio.com/)
  - [PHP IntelliSense extention](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-intellisense)
  - [PHP Debug extention](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-debug)
- [Docker for Mac](https://www.docker.com/docker-mac)

## Usage

```
$ docker-compose up -d
```

### Debugging (Browser)
- Open the project directry with Visual Studio Code.
- Open "www/html/index.php".
- Set a breakpoint at the "phpinfo();" line.
- Start debugging.
  - Open Debug view.
  - Press the green arrow beside "Listen for XDebug".
- Open "http://localhost:8080/index.php" in your web browser.

The program will stop at the breakpoint.

### Debugging (PHPUnit)
- Open the project directry with Visual Studio Code.
- Open "www/src/Calc.php".
- Set a breakpoint at the "$result = $a + $b;" line.
- Start debugging.
  - Open Debug view.
  - Press the green arrow beside "Listen for XDebug".
- Run phpunit.
```
$ docker-compose exec app phpunit src/CalcTest
```

The program will stop at the breakpoint.

If you check "Everything" in the BREAKPOINTS area of Debug view (default), the program also stops when Exceptions occurs.  
Unckeck "Everything" to stop only at breakpoints you set.