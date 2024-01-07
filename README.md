# PHavířP

**_Bo je čas expandovat pyčo_**

## Co?

Bylo to 15. října 2015 kdy Tomáš Kohout poctil Ostravu svým prvním programovacím jazykem, [OSTRAJavou](https://github.com/tkohout/OSTRAJava). Tento čin navždy povznesl Ostravu na vyšší úrovně vědomí, jako důkaz tomu slouží například návštěva Usaina Bolta v roce 2016 či založení Divadla Mír v roce 2017.

## Proč?

Je potřeba dostat Ostravu na internet, to OSTRAJava nesvede. Proto je čas vytvořit nový jazyk, **PHavířP**. Například společnost OKD již reaguje na zrychlený odliv havířů z dolů na web development a [přpravuje se na konec těžby](https://www.idnes.cz/ostrava/zpravy/okd-ostroj-tezba-uhli-utlum-hospodarska-komora.A230418_720553_ostrava-zpravy_jog).

## Už zostravčeno

PHavířP používá příponu `.php`, stejně jako původní PHP, každý program napsaný v PHP je tedy napsaný i v PHavířP.

### Klíčová slova

| banik pyčo | Původní klíčové slovo |
| :--------- | :-------------------- |
| skanduj    | echo                  |
| fajront    | exit                  |
| skap       | die                   |
| dupej      | goto                  |
| klec       | switch                |
| sachta     | case                  |
| veterka    | default               |
| sichta     | while                 |
| brigada    | for                   |
| zdybat     | break                 |
| dlabat     | continue              |
| banik      | try                   |
| pyco       | catch                 |
| zaval      | throw                 |
| rob        | function              |

### Logické operace

| banik pyčo | Původní klíčové slovo |
| :--------- | :-------------------- |
| kaj        | if                    |
| kajtez     | elseif                |
| inak       | else                  |
| aj         | AND                   |
| ci         | OR                    |

### OOP

I PHavířP je objektově orientovaný jazyk a tak nabízí všem Havířům upravenou syntaxi.

| banik pyčo | Původní klíčové slovo |
| :--------- | :-------------------- |
| tryda      | class                 |
| drzka      | interface             |
| davaj      | return                |
| fagan od   | extends               |
| je         | implements            |
| zrob       | new                   |
| nechmatej  | readonly              |
| blembak    | protected             |
| olacka     | private               |
| dul        | public                |

## Použití

Každý program PHavířP začíná slovy `BANIK` a končí slovy `PYCO`.

Typický příklad programu napsaném v PHavířP:

```
BANIK
skanduj "Banik Pyčo Banik Pyčo FCB!";
PYCO
```

Příklad použití dědičnosti v důlním prostředí za pomoci PHavířP:

```
BANIK

drzka Pracujici {
    dul rob makaj();
}

tryda Havir je Pracujici {
    dul $meno;
    dul $pracuje;

    dul rob makaj() {
        skanduj "Rubu uhlí";
    }

    dul rob __construct($meno) {
        $this->meno = $meno;
        $this->pracuje = true;
    }

    dul rob dostanMeno() {
        davaj $this->name;
    }
    dul rob domakal(){
        $this->pracuje = false;
    }
}

tryda Brigadnik fagan od Havir {
    dul $smeny;

    dul rob __construct($meno, $smeny) {
        parent::__construct($meno);

        $this->smeny = $smeny;
    }

    dul rob dostanKonec() {
        davaj $this->smeny;
    }
    dul rob konecSmeny(){
        $this->smeny--;
        kaj ($this->smeny <= 0) {
            $this->domakal();
        }
    }
    dul rob makaj() {
        kaj ($this->smeny <= 0) {
            skanduj "$this->meno už nemá směny\n";
            davaj;
        }
        kajtez ($this->smeny == 1) {
            skanduj "Rubu uhlí naposled\n";
        }
        inak {
            skanduj "Rubu uhlí brigádně\n";
        }
        $this->konecSmeny();
    }
}

$brigadnik = zrob Brigadnik("Jarek Nohavica", 2);
brigada ($i = 0; $i <= $brigadnik->smeny; $i++) {
    $brigadnik->makaj();
}
$havir = zrob Havir("Roman Mrázik");
sichta ($havir->pracuje) {
    $havir->makaj();
}

PYCO
```

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
