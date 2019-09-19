# Over Neural Style Transfer

Jullie hebben zojuist uitleg gehad over de achtergrond van Neural Networks en de Neural Style Transfer techniek.
Voor geïnteresseerden is een van de originele papers waarin dit idee werd toegepast in 2015 [hier](https://arxiv.org/pdf/1508.06576v2.pdf) te vinden.

Deze implementatie en code is origineel geschreven door Anish Athalye, copyright behoort hem dus toe. Zijn github pagina is: https://github.com/anishathalye/neural-style. Hij heeft het vrijgegeven onder GNU GPL 3.0 wat een zeer vrije licentie is en betekent dat je dit voor allerlei implementaties, zelfs commerciele, mag gebruiken zo lang je naar het origineel refereert.

# Installatiehandleiding

Er zijn een aantal stappen die we moeten uitvoeren voordat we dit model zelf kunnen draaien en onze eigen foto's met schilderstijlen kunnen combineren. Een van de stappen is het lokaal krijgen van de code en bestanden die door Anish Athalye met de open-source community gedeeld zijn. Een andere belangrijke stap is het installeren van Python en alle bijbehorende packages. Deze handleiding is ontworpen voor mensen die Python nog niet eerder hebben gebruikt en gaat er dus van uit dat dat nog geinstalleerd moet worden. We gaan in deze beperkte tijd niet in op hoe Python precies werkt maar als er vragen over zijn stel ze natuurlijk vooral.

Bij iedere stap zal ik wat achtergrond informatie geven over hoe het precies in zijn werk gaat (toelichting) en los de acties voor het installeren beschrijven (acties) zodat je alleen dat deel hoeft te lezen als je niet in de achtergrond van een stap geïnteresseerd bent.

## Het lokaal krijgen van de code
### Toelichting GIT
Dit platform, github, is het meest gebruikte platform om open-source code met anderen te delen. Er zijn ook mogelijkheden om code prive te delen met anderen en veel bedrijven hebben dan ook hun eigen, afgeschermde, bedrijfs-git. Naast het delen van code heeft het veel functionaliteiten om gezamenlijk code te schrijven zonder in de problemen te komen. Je kan het je voorstellen alsof je tegelijkertijd in dezelfde online google Sheet Excel werkt als een collega en google er voor zorgt dat je niet tegelijkertijd dezelfde cel aanpast. Zo kan GIT bijhouden dat je niet dezelfde regel code aanpast in een bewerking en daardoor in de problemen komt.

Voor al die bewerkingen wordt het programma GIT gebruikt. Vandaag zullen we dat niet gebruiken omdat het extra stappen kost en we de code toch alleen lokaal willen draaien en niet allemaal tegelijk willen bewerken. Mocht je later geïnteresseerd zijn in GIT of het nu toch willen testen, het programma is <a href="https://git-scm.com/downloads" target="_blank">hier</a> gratis te downloaden.

### Acties
Wat we wel gaan doen is de code simpelweg downloaden. Rechts bovenaan deze pagina vind je een groene knop met "Clone or download". Als je daarop klikt zie je de git URL die je zou kunnen gebruiken als je git gebruikt. Wij gaan echter voor "Download ZIP" waardoor de code als zip folder in je downloads terecht komt. Pak de map uit met je favoriete zip-programma en kopieer de map naar een plek op je laptop waar je hem terug kan vinden.

## Het model downloaden

### Toelichting
Het model is een groot bestand en github is niet gemaakt voor hele grote bestanden. Naast dat het bedrijf de opslagruimte voor bestanden gratis beschikbaar stelt en dus niet wil dat je gigabytes aan bestanden plaatst is het ook onhandig om versie verschillen bij te houden in hele grote bestanden. Het model moet daarom los gedownload worden. Het zal een paar minuten duren dus lees rustig verder terwijl het gedownload wordt. 

### Acties
Het model kan gedownload worden door [hier te klikken][net]. Als de download klaar is verplaats het model dan naar de map met de code die je in de vorige stap gedownload hebt.

## Python

### Toelichting
Zoals eerder beschreven gaan we hier geen uitgebreide instructie over Python geven maar toch wat toelichting. Python is net als R een open-source programmeertaal waarmee je allerlei berekeningen, data analyses en visualisaties kan maken. De syntax, de manier waarop je de taal schrijft, verschilt van R, maar alles dat je in de opleiding in R geleerd hebt is ook op een manier in Python mogelijk. Wat zijn dan belangrijke verschillen? In beide talen zijn verschillende packages beter uitgewerkt door de community. Zo zijn in R meer packages beschikbaar voor uitgebreide statistische analyse en is er in Python meer beschikbaar om hele andere dingen te doen zoals websites bouwen. R is van oudsher een taal ontwikkeld voor en door statistici en data analisten, Python voor en door programmeurs. Daardoor is het in de regel in R makkelijker lokaal op je laptop een gedegen analyse te maken, maar is het in Python makkelijker je analyse aan miljoenen mensen stabiel online beschikbaar te stellen. Voor meer informatie over verschillen tussen beide biedt [deze website een goed overzicht](https://www.guru99.com/r-vs-python.html#targetText=R%20is%20mainly%20used%20for,of%20course%2C%20the%20ideal%20solution).

### Acties
Het meest gebruikte Neural Network package, Tensorflow, dat wij ook gebruiken, werkt nog niet met de laatste versie van Python. We gaan daarom versie 3.6 downloaden. Download het [op deze website](https://www.python.org/downloads/release/python-368/) voor jouw systeem, waarschijnlijk wil je de "Windows x86-64 executable installer" hebben.
In de eeste stap van de installer moet "Add to PATH" worden aangevinkt *(belangrijk!)* zoals in onderstaande afbeelding, verder kunnen de standaard instructies van de installer gevolgd worden.

![Afbeelding](https://vgkits.org/blog/wp-content/uploads/2018/05/windows-add-python-path.jpg)

## IDEs en de command prompt

### Toelichting
Om te ontwikkelen in een programmeertaal gebruik je meestal een Integrated Development Environment (IDE). RStudio is veruit de meest gebruikte IDE voor R, maar je kan in principe een R programma runnen en zelfs schrijven zonder RStudio (geen aanrader). De Python community is verdeelder en er is niet 1 IDE die iedereen gebruikt zoals by R. Veel gebruikte IDEs voor Python zijn:

- [Pycharm](https://www.jetbrains.com/pycharm/)
- [VSCode](https://code.visualstudio.com/)
- [Spyder](https://www.spyder-ide.org/)

Wij zullen vandaag niet met een IDE werken omdat we toch niet zelf python code gaan schrijven en dat weer extra stappen vereist. Als je Python hebt geïnstalleerd kan je bestaande script ook runnen vanaf de command prompt en dat is wat we vandaag zullen doen. Als je later deze scripts of andere wilt bewerken is het aan te raden wel een van bovenstaande IDEs te gebruiken.

### Acties
De command prompt moet geopend worden in de folder met de gedownloade code. De makkelijkste manier om dit te doen is om in de verkenner naar de juiste folder te gaan en shift+rechtermuis te klikken. De shift voegt opties aan het menu toe en je ziet nu waarschijnlijk "open PowerShell window here" of "open command prompt here", daar klik je op. Een nieuw venster opent waar je commando's kan typen. Om de command prompt te laten weten dat je een python script wil draaien type je `python naam-van-jouw-script` waarbij je `naam-van-jouw-script` vervangd met de bestandsnaam van het Python bestand. Test het nu door `python test_python.py` te runnen. Runnen gebruiken we als afkorting voor "typ dit commando in het command prompt en druk op enter". Als het goed is draait dit het testscript in de map en je zou een aanmoedigende boodschap moeten zien.

## Python packages

### Toelichting
Net als in R kun je met een "kale" Python installatie nog niet heel veel en moet je packages installeren om echt interessant werk te kunnen doen. Hier onder volgt een overzicht van de drie belangrijkste R packages waar we mee hebben leren werken en hun Python tegenhangers:

| Doel | R Pacakge | Python Package |
| --- | --- | --- |
| Data en tabelbewerkingen | dplyr | pandas |
| Visualisatie (plots) | ggplot | matplotlib (of plotly) |
| Machine learning| caret | scikit-learn |

Nadat je Python hebt geinstalleerd kan je een package los installeren vanaf de command prompt met `pip install <package naam>`, dus bijvoorbeeld `pip install pandas`. Je kan ook meerdere packages in 1 keer installeren. Al onze benodigde packages staan in het bestand `requirements.txt` en met het commando `pip install -r requirements.txt` zullen deze allemaal geinstalleerd worden. 

### Acties
In de command prompt run je `pip install -r requirements.txt`.
Krijg je een error dan kan het zijn dat je een dependency mist, vraag het aan een van ons!

## Runnen!

### Toelichting
Je bent er eindelijk klaar voor om met behulp van Neural Networks een schilderstijl toe te gaan passen op een foto. Of dat nou een mooi resultaat gaat opleveren of niet, je hebt onderweg geleerd hoe de open-source community werkt, python aan de praat gekregen en geleerd hoe je packages installeert. Al een mooi resultaat op zichzelf!

### Acties
Vanaf de commandline kun je met dit commando een afbeelding produceren (alles tussen <> is een voorbeeld, je typt normaal de <> niet daadwerkelijk):

`python neural_style.py --content <content file> --styles <style file> --output <output file>`

Dus bijvoorbeeld met:

`python neural_style.py --content examples/emiel.jpg --styles examples/1-style.jpg --output examples/output_foto.jpg`

Je kan tekst zoals deze naar de command prompt plakken door normaal te kopieren (ctrl+c) en te plakken met shift+insert in de command prompt. Zet in de examples folder je eigen foto's, pas het commando aan en runnen! Er kunnen warnings gegeven worden dat is over het algemeen geen probleem. Errors zijn natuurlijk wel een probleem. Na een tijdje moet je gaan zien dat er iteraties gaan lopen met een geschatte tijd die het nog duurt tot het script gedraaid is.

Pas op: runnen duurt lang, makkelijk een half uur. Het duurt langer voor grotere afbeeldingen en onze smartphones maken erg scherpe grote afbeeldingen. Probeer foto's kleiner dan 600x600 pixels te gebruiken. Grotere foto's kunnen in kwaliteit worden teruggebracht met websites als deze: https://resizeimage.net/. Of met lokale software als het foto's zijn die je niet zomaar naar iedere website wil uploaden.

Er zijn nog allerlei extra opties die je aan of uit kan zetten. Kijk daarvoor op de originele github pagina: https://github.com/anishathalye/neural-style

## License

Copyright (c) 2015-2019 Anish Athalye. Released under GPLv3. See
[LICENSE.txt][license] for details.

[net]: http://www.vlfeat.org/matconvnet/models/imagenet-vgg-verydeep-19.mat
[license]: LICENSE.txt
