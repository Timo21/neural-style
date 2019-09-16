# Over Neural Style Transfer

Jullie hebben zojuist uitleg gehad over de achtergrond van Neural Networks en de Neural Style Transfer techniek.
Voor geïnteresseerden is een van de originele papers waarin dit idee werd toegepast in 2015 [hier](https://arxiv.org/pdf/1508.06576v2.pdf) te vinden.

Deze implementatie en code is origineel geschreven door Anish Athalye, copyright behoort hem dus toe. Zijn github pagina is: https://github.com/anishathalye/neural-style. Hij heeft het vrijgegeven onder GNU GPL 3.0 wat een zeer vrije licentie is en betekent dat je dit voor allerlei implementaties, zelfs commerciele, mag gebruiken zo lang je het origineel maar correct citeert. Ik heb kleine aanpassingen gedaan om het nog makkelijker out-of-the-box te laten werken.

# Installatiehandleiding

Er zijn een aantal stappen die we moeten uitvoeren voordat we dit model zelf kunnen draaien en onze eigen foto's met schilderstijlen kunnen combineren. Een van de stappen is het lokaal krijgen van de code en bestanden die door Anish Athalye met de open-source community gedeeld zijn. Een andere belangrijke stap is het installeren van Python en alle bijbehorende libraries (packages). Deze handleiding is ontworpen voor mensen die Python nog niet eerder hebben gebruikt en gaat er dus van uit dat dat nog geinstalleerd moet worden. We gaan in deze beperkte tijd niet in op hoe Python precies werkt maar als er vragen over zijn stel ze natuurlijk vooral.

Bij iedere stap zal ik wat achtergrond informatie geven over hoe het precies in zijn werk gaat (toelichting) en los de acties voor het installeren beschrijven (acties) zodat je alleen dat deel hoeft te lezen als je niet in de achtergrond van een stap geïnteresseerd bent.

## Het lokaal krijgen van de code
### Toelichting GIT
Dit platform, github, is het meest gebruikte platform om open-source code met anderen te delen. Er zijn ook mogelijkheden om code prive te delen met anderen en veel bedrijven hebben dan ook hun eigen, afgeschermde, bedrijfs-git. Naast het delen van code heeft het veel functionaliteiten om gezamenlijk code te schrijven zonder in de problemen te komen. Je kan het je voorstellen alsof je tegelijkertijd in dezelfde online google Sheet Excel werkt als een collega en google er voor zorgt dat je niet tegelijkertijd dezelfde cel aanpast. Zo kan GIT bijhouden dat je niet dezelfde regel code aanpast in een bewerking en daardoor in de problemen komt.

Voor al die bewerkingen wordt het programma GIT gebruikt. Vandaag zullen we dat niet gebruiken omdat het extra stappen kost en we de code toch alleen lokaal willen draaien en niet allemaal tegelijk willen bewerken. Mocht je later geïnteresseerd zijn in GIT of het nu toch willen testen, het programma is [hier](https://github.com/anishathalye/neural-style) gratis te downloaden.

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
Download de laatste versie van Python door [op deze website](https://www.python.org/downloads/) op de gele download knop te klikken.
In de eeste stap van de installer moet "Add to PATH" worden aangevinkt *(belangrijk!)* zoals in onderstaande afbeelding, verder kunnen de standaard instructies van de installer gevolgd worden.

![Afbeelding](https://vgkits.org/blog/wp-content/uploads/2018/05/windows-add-python-path.jpg)

## De command line

### Toelichting

### Acties

## Python libraries

### Toelichting

### Acties

## Runnen!

### Toelichting

### Acties

## Related Projects

See [here][lengstrom-fast-style-transfer] for an implementation of [fast
(feed-forward) neural style][fast-neural-style] in TensorFlow.

**[Try neural style](https://tenso.rs/demos/fast-neural-style/) client-side in
your web browser without installing any software (using
[TensorFire](https://tenso.rs/)).**

## Running

`python neural_style.py --content <content file> --styles <style file> --output <output file>`

Run `python neural_style.py --help` to see a list of all options.

If you are running this project on [Floydhub](https://www.floydhub.com) you can use the following syntax (this pulls in the pre-trained VGG network automatically):

`floyd run --gpu --env tensorflow-1.3
--data  floydhub/datasets/imagenet-vgg-verydeep-19/3:vgg
"python neural_style.py --network /vgg/imagenet-vgg-verydeep-19.mat --content <content file> --styles <style file> --output <output file>"`


Use `--checkpoint-output` and `--checkpoint-iterations` to save checkpoint images.

Use `--iterations` to change the number of iterations (default 1000).  For a 512×512 pixel content file, 1000 iterations take 60 seconds on a GTX 1080 Ti, 90 seconds on a Maxwell Titan X, or 60 minutes on an Intel Core i7-5930K. Using a GPU is highly recommended due to the huge speedup.

## Example 1

Running it for 500-2000 iterations seems to produce nice results. With certain
images or output sizes, you might need some hyperparameter tuning (especially
`--content-weight`, `--style-weight`, and `--learning-rate`).

The following example was run for 1000 iterations to produce the result (with
default parameters):

![output](examples/1-output.jpg)

These were the input images used (me sleeping at a hackathon and Starry Night):

![input-content](examples/1-content.jpg)

![input-style](examples/1-style.jpg)

## Example 2

The following example demonstrates style blending, and was run for 1000
iterations to produce the result (with style blend weight parameters 0.8 and
0.2):

![output](examples/2-output.jpg)

The content input image was a picture of the Stata Center at MIT:

![input-content](examples/2-content.jpg)

The style input images were Picasso's "Dora Maar" and Starry Night, with the
Picasso image having a style blend weight of 0.8 and Starry Night having a
style blend weight of 0.2:

![input-style](examples/2-style1.jpg)
![input-style](examples/2-style2.jpg)

## Tweaking

`--style-layer-weight-exp` command line argument could be used to tweak how "abstract"
the style transfer should be. Lower values mean that style transfer of a finer features
will be favored over style transfer of a more coarse features, and vice versa. Default
value is 1.0 - all layers treated equally. Somewhat extreme examples of what you can achieve:

![--style-layer-weight-exp 0.2](examples/tweaks/swe02.jpg)
![--style-layer-weight-exp 2.0](examples/tweaks/swe20.jpg)

(**left**: 0.2 - finer features style transfer; **right**: 2.0 - coarser features style transfer)

`--content-weight-blend` specifies the coefficient of content transfer layers. Default value -
1.0, style transfer tries to preserve finer grain content details. The value should be
in range [0.0; 1.0].

![--content-weight-blend 1.0](examples/tweaks/cwe10_default.jpg)
![--content-weight-blend 0.1](examples/tweaks/cwe01.jpg)

(**left**: 1.0 - default value; **right**: 0.1 - more abstract picture)

`--pooling` allows to select which pooling layers to use (specify either `max` or `avg`).
Original VGG topology uses max pooling, but the [style transfer paper][paper] suggests
replacing it with average pooling. The outputs are perceptually different, max pool in
general tends to have finer detail style transfer, but could have troubles at
lower-freqency detail level:

![--pooling max](examples/tweaks/swe14_pmax.jpg)
![--pooling avg](examples/tweaks/swe14_pavg.jpg)

(**left**: max pooling; **right**: average pooling)

`--preserve-colors` boolean command line argument adds post-processing step, which
combines colors from the original image and luma from the stylized image (YCbCr color
space), thus producing color-preserving style transfer:

![--pooling max](examples/tweaks/swe14_pmax.jpg)
![--pooling max](examples/tweaks/swe14_pmax_pcyuv.jpg)

(**left**: original stylized image; **right**: color-preserving style transfer)

## Requirements

### Data Files

* [Pre-trained VGG network][net] (MD5 `106118b7cf60435e6d8e04f6a6dc3657`) - put it in the top level of this repository, or specify its location using the `--network` option.

### Dependencies

You can install Python dependencies using `pip install -r requirements.txt`,
and it should just work. If you want to install the packages manually, here's a
list:

* [TensorFlow](https://www.tensorflow.org/versions/master/get_started/os_setup.html#download-and-setup)
* [NumPy](https://github.com/numpy/numpy/blob/master/INSTALL.rst.txt)
* [SciPy](https://github.com/scipy/scipy/blob/master/INSTALL.rst.txt)
* [Pillow](http://pillow.readthedocs.io/en/3.3.x/installation.html#installation)

## Citation

If you use this implementation in your work, please cite the following:

```
@misc{athalye2015neuralstyle,
  author = {Anish Athalye},
  title = {Neural Style},
  year = {2015},
  howpublished = {\url{https://github.com/anishathalye/neural-style}},
  note = {commit xxxxxxx}
}
```

## License

Copyright (c) 2015-2019 Anish Athalye. Released under GPLv3. See
[LICENSE.txt][license] for details.

[net]: http://www.vlfeat.org/matconvnet/models/imagenet-vgg-verydeep-19.mat
[paper]: http://arxiv.org/pdf/1508.06576v2.pdf
[l-bfgs]: https://en.wikipedia.org/wiki/Limited-memory_BFGS
[adam]: http://arxiv.org/abs/1412.6980
[ad]: https://en.wikipedia.org/wiki/Automatic_differentiation
[lengstrom-fast-style-transfer]: https://github.com/lengstrom/fast-style-transfer
[fast-neural-style]: https://arxiv.org/pdf/1603.08155v1.pdf
[license]: LICENSE.txt
