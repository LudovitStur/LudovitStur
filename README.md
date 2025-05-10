<!DOCTYPE html>
<html lang="sk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Upchatá Diaľnica D1</title>
  <style>
    body {
      background-color: #0a0a0a;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 40px;
    }

    h1 {
      color: #00f;
      font-size: 2.5em;
    }

    .button {
      background-color: #8a2be2;
      color: white;
      border: none;
      padding: 15px 25px;
      font-size: 1.2em;
      margin: 10px;
      cursor: pointer;
      border-radius: 5px;
    }

    .button:hover {
      background-color: #7a1dbf;
    }

    .content {
      display: none;
      opacity: 0;
      transition: opacity 0.5s ease, transform 0.5s ease;
      transform: translateY(20px);
    }

    .content.visible {
      display: block;
      opacity: 1;
      transform: translateY(0);
    }

    .back-button {
      background-color: #f44336;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Ak si sa ocitol na upchatej diaľnici D1:</h1>
  <p>Toto je stránka, ktorá ti pomôže vyriešiť rôzne problémy, ak sa ocitneš v zápche na diaľnici D1 v smere do Trenčína alebo z Trenčína.</p>
  
  <button class="button" onclick="showContent('policajti')">Policajti a platy</button>
  <button class="button" onclick="showContent('sestra')">Sestra, Pes a Santa/Mikuláš</button>
  <button class="button" onclick="showContent('vecko')">Potreba ísť na vecko</button>
  <button class="button" onclick="showContent('armada')">Fyzická pomoc a armáda</button>
  <button class="button" onclick="showContent('luster')">Luster</button>

  <div id="policajti" class="content">
    <p>Rozumiem, že situácia na upchatej diaľnici D1 môže byť stresujúca, hlavne keď si spomenieš na to, aké majú niektoré profesie platy za to, že nič nerobia, a že v takýchto zložitých situáciách, keď ide ľuďom o život, nepomáhajú. Policajti majú síce veľké platy, pri takýchto situáciách ale nemusia stíhať prísť. Preto sa na nich netreba hnevať. Hlavne zostaň pokojný a snaž sa nevyrobiť ďalšie problémy.</p>
    <button class="button back-button" onclick="goBack()">Dobre</button>
  </div>

  <div id="sestra" class="content">
    <p>Tvoja sestra sa začala hrať na psa alebo Mikuláša a hovorí, že pes sa rovná Santa, lebo pes robí hau-hau-hau a Santa robí hou-hou-hou. V tejto situácii, ktorá môže byť veľmi stresujúca, nepokladaj svoju sestru za divnú alebo psychicky nestabilnú. Dokonca môže byť vhodná alternatíva pridať sa. Môže ti to pomôcť odbúrať stres.</p>
    <button class="button back-button" onclick="goBack()">Dobre</button>
  </div>

  <div id="vecko" class="content">
    <p>Ak máš potrebu ísť na záchod a vykonať potrebu a v blízkosti nič podobného nie je, skús vyhľadať miesto, kde ťa nikto nevidí. Ak nič také nenájdeš, skús urobiť to možno medzi autami. V takej situácii každý pochopí, že keď proste musíš, tak musíš. Ak si "to" ale nestihol a už si to urobil, je veľmi pravdepodobné, že si sa vyčúral na čelné sklo susedného auta a vodič v ňom sa na teba veľmi hnevá, lebo cezeň nič nevidí, no podarilo sa ti zabarikádovať dvere. V takom prípade sa snaž nenahnevať ho ešte viac a dostať sa čo najrýchlejšie do bezpečia svojho auta.</p>
    <button class="button back-button" onclick="goBack()">Dobre</button>
  </div>

  <div id="armada" class="content">
    <p>V tejto situácii je veľmi pravdepodobné, že chcete privolať záchranné zložky štátu, napríklad armádu, prípadne celé Impérium. Môže byť aj medzigalaktické, čiže vesmírne, kľudne aj zo Star Wars.</p>
    <p>Chceš, aby som privolal Impérium?</p>
    <button class="button" onclick="playSoundAndShow('imperiumResponse', 'imperium-sound.mp3')">Áno</button>
    <button class="button back-button" onclick="goBack()">Nie</button>
  </div>

  <div id="imperiumResponse" class="content">
    <p>Impérium je na ceste, pripravené zasiahnuť.</p>
    <button class="button back-button" onclick="goBack()">Dobre</button>
  </div>

  <div id="luster" class="content">
    <p>Luster sa už blíži. Už je skoro tam. Treba si naň dávať veľký pozor. Nemôžeš ho rozbiť, lebo príde babička Zuzanka a bude sa veľmi hnevať. Nemôže ho rozbiť NIKTO. Kvôli tomuto lustru je tu možnosť privolať Darth Vadera.</p>
    <p>Chceš privolať Darth Vadera na ochranu Lustra?</p>
    <button class="button" onclick="playSoundAndShow('vaderResponse', 'vader-sound.mp3')">Áno</button>
    <button class="button back-button" onclick="goBack()">Nie</button>
  </div>

  <div id="vaderResponse" class="content">
    <p>Darth Vader je na ceste. Možno príde aj spolu s Impériom, ktorému môže veliť. Takže pod takouto ochranou už nedôjde k žiadnemu nenahlásenému úniku tekutiny, tvoj luster bude v bezpečí a neodštiepi sa ani jedna sklenená črepinka.</p>
    <button class="button back-button" onclick="goBack()">Dobre</button>
  </div>

  <script>
    function showContent(id) {
      document.querySelectorAll('.content').forEach(function (element) {
        element.style.display = 'none';
        element.classList.remove('visible');
      });
      const target = document.getElementById(id);
      target.style.display = 'block';
      setTimeout(() => target.classList.add('visible'), 10);
    }

    function goBack() {
      document.querySelectorAll('.content').forEach(function (element) {
        element.style.display = 'none';
        element.classList.remove('visible');
      });
    }

    function playSoundAndShow(id, soundFile) {
      const audio = new Audio(soundFile);
      audio.play();
      showContent(id);
    }
  </script>
</body>
</html>
