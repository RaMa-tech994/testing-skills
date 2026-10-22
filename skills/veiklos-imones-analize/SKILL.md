---
name: veiklos-imones-analize
description: Orkestruoja visą įmonės analizės procesą paeiliui naudodamas veiklos-apzvalga-duomenys, veiklos-apzvalga-analize ir veiklos-apzvalga-isvada įgūdžius. Naudok, kai vartotojas nurodo įmonę ir nori gauti pilną Okredo finansinių duomenų analizę bei struktūruotą galutinę išvadą.
---

# Įmonės veiklos analizės workflow

## Tikslas

Vienu vartotojo prašymu paeiliui įvykdyti tris esamus įgūdžius ir pateikti vieną galutinį rezultatą, pavadintą **„Veiklos įmonės analizė“**. Šis įgūdis yra proceso koordinatorius: jis pats nepakeičia atskirų įgūdžių duomenų rinkimo, analizės ar išvadų rengimo instrukcijų.

## Privaloma vykdymo seka

### 1 etapas — finansinių duomenų surinkimas

Paleisk ir vykdyk `veiklos-apzvalga-duomenys` įgūdį.

- Įvestis: vartotojo nurodytas įmonės pavadinimas ir / arba juridinio asmens kodas.
- Rezultatas: patvirtinta įmonė, jos kodas, Okredo profilio URL, patikrinimo data, prieinami finansiniai rodikliai pagal metus, valiuta / vienetai ir duomenų ribotumai.
- Patikrink, ar įmonė identifikuota patikimai. Jei ne, sustok ir paprašyk vartotojo patikslinimo. Nevykdyk tolesnių etapų su netinkamos įmonės duomenimis.
- Jei finansų skiltis neprieinama, išsaugok šį apribojimą ir tęsk tik tiek, kiek leidžia patikimi turimi duomenys.

### 2 etapas — finansinių rodiklių analizė

Tik gavęs 1 etapo rezultatus, paleisk `veiklos-apzvalga-analize` įgūdį.

- Perduok visus surinktus rodiklius, metus, valiutą, šaltinio nuorodą ir duomenų ribotumus.
- Gauk pajamų, pelno ir kitų turimų rodiklių tendencijų palyginimą, pagrįstus skaičiavimus ir atsargias interpretacijas.
- Neleisk analizei remtis rodikliais, kurių 1 etapas nepatvirtino.
- Jei duomenų nepakanka, analizės rezultatas turi aiškiai nurodyti šį ribotumą, o ne sukurti nepagrįstas išvadas.

### 3 etapas — galutinė santrauka ir išvados

Tik gavęs 1 ir 2 etapų rezultatus, paleisk `veiklos-apzvalga-isvada` įgūdį.

- Perduok jam pirminius finansinius duomenis ir analizės rezultatus.
- Paprašyk sujungti juos į struktūruotą galutinę ataskaitą su svarbiausiais rodikliais, 3–5 pagrindinėmis išvadomis, dėmesio signalais, duomenų ribotumais ir šaltiniais.
- Jei surinkti duomenys ir analizės rezultatai prieštarauja vienas kitam, nepaslėpk neatitikimo: pažymėk jį ir nurodyk, kad reikia patikrinti pirminį šaltinį.
- Neišgalvok finansinių duomenų ir nepateik garantuotų finansinio patikimumo, kredito ar investavimo išvadų.

## Galutinio rezultato formatas

Galutinį atsakymą pateik vienu rezultatu su pavadinimu:

# Veiklos įmonės analizė — [įmonės pavadinimas]

Rezultate turi būti:

1. **Įmonės identifikacija:** pavadinimas, kodas, Okredo profilio nuoroda ir patikrinimo data, jei žinoma.
2. **Trumpa santrauka:** keli sakiniai apie pagrindinę finansinę kryptį.
3. **Finansinių rodiklių lentelė:** naujausi ir ankstesni turimi metai, reikšmės, valiuta ir pokyčiai.
4. **Pagrindinės išvados:** 3–5 aiškiai suformuluotos, skaičiais pagrįstos įžvalgos.
5. **Dėmesio signalai ir ribotumai:** nepalankūs ar neįprasti pokyčiai, trūkstami duomenys ir prieigos apribojimai.
6. **Galutinė išvada:** trumpas, subalansuotas apibendrinimas, atskiriantis faktus nuo interpretacijos.

Praleisk rodiklius, kurių nėra, ir aiškiai įvardyk duomenų trūkumus. Visus finansinius skaičius susiek su konkrečiais metais ir valiuta. Pridėk šaltinio nuorodą, kai ji prieinama.

## Workflow vykdymo patikra

Prieš pateikdamas galutinį atsakymą, patikrink:

- [ ] 1 etapas — `veiklos-apzvalga-duomenys` įvykdytas arba aiškiai nurodyta, kodėl negalėjo būti įvykdytas.
- [ ] 2 etapas — `veiklos-apzvalga-analize` įvykdytas remiantis 1 etapo duomenimis arba pažymėta, kodėl analizė ribota.
- [ ] 3 etapas — `veiklos-apzvalga-isvada` įvykdytas remiantis abiejų ankstesnių etapų rezultatais arba pažymėta, kodėl galutinė išvada ribota.
- [ ] Visuose etapuose kalbama apie tą pačią įmonę.
- [ ] Nėra išgalvotų rodiklių ar nepatvirtintų šaltinio teiginių.
- [ ] Galutinis atsakymas pavadintas „Veiklos įmonės analizė — [įmonės pavadinimas]“.

## Vykdymo aplinkos apribojimas

Tai agento workflow instrukcija, o ne savarankiškas vykdomas GitHub Actions procesas. Jį vykdantis agentas turi realiai iškviesti tris nurodytus įgūdžius paeiliui, perduodamas kiekvieno etapo rezultatus kitam etapui. Jei vykdymo aplinka negali iškviesti įgūdžių tiesiogiai, aiškiai tai nurodyk ir vykdyk jų instrukcijas paeiliui, jei jos prieinamos.
