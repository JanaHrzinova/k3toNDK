# Kramerius 3 → NDK

Jednoduchá webová aplikace pro vyhledání odpovídajícího dokumentu v Národní digitální knihovně (NDK) podle identifikátoru **Handle** používaného v systému **Kramerius 3 (K3)**.

Aplikace je určena především pro pracovníky Národní knihovny ČR a další uživatele, kteří potřebují převádět starší odkazy z Krameria 3 na odpovídající dokumenty v NDK.

## Funkce

Aplikace nabízí dva režimy práce:

- **Jednotlivé vyhledávání**
  - vyhledání jednoho dokumentu podle Handle,
  - zobrazení základních metadat,
  - zobrazení náhledu dokumentu (pokud je dostupný),
  - otevření dokumentu v NDK,
  - kopírování UUID,
  - kopírování Handle.

- **Hromadné vyhledávání**
  - zpracování více identifikátorů Handle najednou,
  - export výsledků do CSV,
  - kopírování nalezených UUID.

## Podporované vstupy

Lze zadat:

```
ABA001/12370785
```

nebo

```
handle:ABA001/12370785
```

nebo celý odkaz

```
http://kramerius.nkp.cz/kramerius/handle/ABA001/12370785
```

## Vyhledávání

Aplikace využívá veřejné API Kramerius 7.

Vyhledávání probíhá podle pole:

```
id_other
```

s hodnotou

```
handle:ABA001/...
```

Po nalezení dokumentu aplikace zobrazí:

- název dokumentu,
- typ dokumentu,
- rok vydání,
- číslo stránky (je-li dostupné),
- UUID,
- původní Handle.

## Typy dokumentů

Aplikace rozlišuje zejména:

- monografie,
- periodika,
- ročníky periodik,
- čísla periodik,
- stránky,
- články,
- mapy,
- grafiky,
- rukopisy,
- notové tisky,
- zvukové dokumenty.

Pro stránky monografií a periodik jsou zobrazovány odpovídající názvy dokumentů.

## Náhled dokumentu

Pokud je náhled dostupný, zobrazí se titulní obrázek dokumentu.

Pokud náhled není dostupný, aplikace výsledek zobrazí bez náhledu.

## Nenalezený dokument

Pokud dokument není v NDK nalezen, aplikace nabídne přímý odkaz na otevření dokumentu v systému Kramerius 3.

## Omezení

Migrace dokumentů z Krameria 3 do Národní digitální knihovny stále probíhá.

V minulosti byly při migraci identifikátory Handle zachovány pouze u části dokumentů. Proto nemusí být podle některých Handle možné dokument v NDK nalézt, přestože již byl do NDK převeden.

Metadata jsou průběžně doplňována a identifikátory Handle jsou postupně přidávány i na další úrovně dokumentů.

## Technologie

- HTML5
- CSS3
- JavaScript (ES6)
- veřejné API Kramerius 7

Aplikace je čistě klientská a nevyžaduje žádný server ani backend.

## Spuštění

Stačí otevřít soubor `index.html` nebo publikovat obsah repozitáře například pomocí **GitHub Pages**.

## Autor

Jana Hrzinová

Vyrobeno za pomoci ChatGPT 5.5.
