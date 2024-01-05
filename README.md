# PHavířP

**_Bo je čas expandovat pyčo_**

## Co?

Bylo to 15. října 2015 kdy Tomáš Kohout poctil Ostravu svým prvním programovacím jazykem, [OSTRAJavou](https://github.com/tkohout/OSTRAJava).tento čin navždy povznesl Ostravu na vyšší úrovně vědomí, jako důkaz tomu slouží například založení divadla Mír v roce 2017 či návštěva Usainem Boltem v roce 2016.

## Proč?

Je potřeba dostat Ostravu na internet, to OSTRAJava nesvede. Proto je čas vytvořit nový jazyk, **PHavířP**.

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

# Kompilování

1. Spusť `./buildconf`
2. Spusť `./configure --prefix <where_to_install_php>`
3. Spusť `make`
4. Spusť `make install`

Právě jsi zostravčil PHP, gratuluju.<br>
(Jo a první volání `make` může chvilku zabrat)

# Inspirační

Vznik PHavířP byl inspirován [OSTRAJavou](https://github.com/tkohout/OSTRAJava) a [PHPkem jejího veličenstva](https://github.com/samuelbsource/her-majesty-php)
