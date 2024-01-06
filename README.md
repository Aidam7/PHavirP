# PHavířP

**_Bo je čas expandovat pyčo_**

## Co?

Bylo to 15. října 2015 kdy Tomáš Kohout poctil Ostravu svým prvním programovacím jazykem, [OSTRAJavou](https://github.com/tkohout/OSTRAJava). Tento čin navždy povznesl Ostravu na vyšší úrovně vědomí, jako důkaz tomu slouží například návštěva Usaina Bolta v roce 2016 či založení divadla Mír v roce 2017.

## Proč?

Je potřeba dostat Ostravu na internet, to OSTRAJava nesvede. Proto je čas vytvořit nový jazyk, **PHavířP**. Například společnost OKD již reaguje na zrychlený odliv havířů z dolů na web development a [přpravuje se na konec těžby](https://www.idnes.cz/ostrava/zpravy/okd-ostroj-tezba-uhli-utlum-hospodarska-komora.A230418_720553_ostrava-zpravy_jog).

## Použití

Typický příklad programu napsaném v PHavířP:

```
<?php
skanduj "Banik Pyčo Banik Pyčo FCB!";
?>
```

## Už zostravčeno

PHavířP používá příponu `.php`, stejně jako původní PHP, každý program napsaný v PHP je tedy napsaný i v PHavířP.

### Klíčová slova

| banik pyčo | Původní klíčové slovo |
| :--------- | :-------------------- |
| fajront    | exit                  |
| skap       | die                   |
| dupej      | goto                  |
| zdybat     | break                 |
| dlabat     | continue              |
| tryda      | class                 |
| klec       | switch                |
| sachta     | case                  |
| dno        | default               |
| sichta     | while                 |
| brigada    | for                   |
| fagan od   | extends               |
| je         | implements            |
| banik      | try                   |
| pyco       | catch                 |
| zaval      | throw                 |
| skanduj    | echo                  |

### Logické operace

| banik pyčo | Původní klíčové slovo |
| :--------- | :-------------------- |
| kaj        | if                    |
| kajtez     | elseif                |
| inak       | else                  |
| aj         | AND                   |
| ci         | OR                    |

### Datové typy

Sice tím není PHP známé, ale i přesto nabízí PHavířP vlastní typy, protože stavíme na vyšší verzi PHP než je 7.4

| banik pyčo | Původní klíčové slovo |
| :--------- | :-------------------- |
| cyslo      | int                   |
| desetinne  | double                |
| desetinne  | float                 |
| bul        | bool                  |
| dryzt      | string                |
| zrob       | new                   |
| nechmatej  | readonly              |
| blembak    | protected             |
| olacka     | private               |
| dul        | public                |

## Jak zostravčit?

Klíčová slova se nachází v: `Zend/zend_language_scanner.l`<br>
Kousek pod komentářem `/* compute yyleng before each rule */` se nachází definice klíčových slov

Vypadá to nějak takhle

```
<ST_IN_SCRIPTING>"goto" {
    RETURN_TOKEN_WITH_IDENT(T_GOTO);
}
```

Chceš teda "zostravčit" klíčové slovo _goto_ na _dupej_ ?

Jako první zkopíruj:

```
<ST_IN_SCRIPTING>"goto" {
    RETURN_TOKEN_WITH_IDENT(T_GOTO);
}
```

A vlož ho pod komentář `/* banik pyčo */`

Pak přepiš:

```
<ST_IN_SCRIPTING>"goto" {
```

Na:

```
<ST_IN_SCRIPTING>"dupej" {
```

Pokud nejsi cyp tak ti půjde zkompilovat PHavířP.

## Kompilování pro Windows

[Zde.](https://github.com/php/php-sdk-binary-tools#basic-usage-example)

## Kompilování pro Linux

0. Nastav práva na 777: `sudo chmod 777 -R <cyp>/`
1. Nainstaluj tyhle cypy `sudo apt install -y pkg-config build-essential autoconf bison re2c libxml2-dev libsqlite3-dev`
2. Spusť `./buildconf`
3. Spusť `./configure`
4. Spusť `make` (Jestli to poprvý netrvá dlouho tak je něco špatně)
5. Spusť `make install`

---

Právě jsi zostravčil PHP, gratuluju.<br>

## Jak pomoct Ostravě?

Můžeš mi otevřít pull request, snad mě do té doby nikdo nevezme lopatou.

## Inspirační

Vznik PHavířP byl inspirován [OSTRAJavou](https://github.com/tkohout/OSTRAJava) a [PHPkem jejího veličenstva](https://github.com/samuelbsource/her-majesty-php).
