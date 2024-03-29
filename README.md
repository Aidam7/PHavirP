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
| zaval      | throw                 |
| zkusaj     | try                   |
| skripni    | catch                 |
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
| stodolni   | public                |

## Použití

Každý program PHavířP začíná slovy `BANIK` a končí slovy `PYCO`. Místo středníků používá, jak jinak, zvučné ` pyco`.

Typický příklad programu napsaném v PHavířP:

```
BANIK
skanduj "Toz vitaj!" pyco
PYCO
```

Příklad použití dědičnosti v důlním prostředí za pomoci PHavířP:

```
BANIK

drzka Pracujici {
    stodolni rob makaj() pyco
}

tryda Havir je Pracujici {
    stodolni $meno pyco
    stodolni $pracuje pyco

    stodolni rob makaj() {
        skanduj "Rubu uhlí" pyco
    }

    stodolni rob __construct($meno) {
        $this->meno = $meno pyco
        $this->pracuje = true pyco
    }

    stodolni rob dostanMeno() {
        davaj $this->name pyco
    }
    stodolni rob domakal(){
        $this->pracuje = false pyco
    }
}

tryda Brigadnik fagan od Havir {
    stodolni $smeny pyco

    stodolni rob __construct($meno, $smeny) {
        parent::__construct($meno) pyco

        $this->smeny = $smeny pyco
    }

    stodolni rob dostanKonec() {
        davaj $this->smeny pyco
    }
    stodolni rob konecSmeny(){
        $this->smeny-- pyco
        kaj ($this->smeny <= 0) {
            $this->domakal() pyco
        }
    }
    stodolni rob makaj() {
        kaj ($this->smeny <= 0) {
            skanduj "$this->meno už nemá směny\n" pyco
            davaj pyco
        }
        kajtez ($this->smeny == 1) {
            skanduj "Rubu uhlí naposled\n" pyco
        }
        inak {
            skanduj "Rubu uhlí brigádně\n" pyco
        }
        $this->konecSmeny() pyco
    }
}

$brigadnik = zrob Brigadnik("Jarek Nohavica", 2) pyco
brigada ($i = 0 pyco $i <= $brigadnik->smeny pyco $i++) {
    $brigadnik->makaj() pyco
}
$havir = zrob Havir("Roman Mrázik") pyco
sichta ($havir->pracuje) {
    $havir->makaj() pyco
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
