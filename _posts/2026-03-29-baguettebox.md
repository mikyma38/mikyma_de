---
layout: post
title: "BaguetteBox.js - Galerie Script"
categories: Bits_Bytes
tags: [Computer,Internet,Jekyll]
image: baguetteBox.jpg
---
## Endlich geschafft: Eine Lightbox Galerie in die Webseite integrieren 

Die [Baguettebox Galerie][1] , geschrieben in reinem javascript , ist wirklich leicht
in Jekyll zu integrieren! lediglich die beiden Dateien aus dem [dist Verzeichnis][3] des reposority per Script Tag ins Dokument laden

```html
<link rel="stylesheet" href="css/baguetteBox.min.css">
<script src="js/baguetteBox.min.js" async></script>
```

und am Ende des Dokuments nochmal per Event handler starten.  

```html
<script>
window.addEventListener('load', function() {
  baguetteBox.run('.gallery');
});
</script>
```
  
Auf der Projekt seite ist das leicht verständlich [dokumentiert in der Readme.md][2] .

Hier in Jekyll hab ich dann eben im header aller seiten, abhängig von ner Frontmatter Variable die anzeigt ob die entsprechende Seite ne Galerie enthält, 
die Scripte geladen.  
Im footer, ebenfalls abhängig von der FrontMatter Variable im Post, den Eventhandler per script Tag eingebunden. Der Eventhandler sollte erst aufgerufen werden wenn das Dokument ziemlich fertig in den Browser geladen ist.

In den Artikel'n [Meeries Zuause][4] und [Vogesen][5] seht ihr die Galerie im Einsatz.Einfach einen Container um alle Bilder die in groß angezeigt werden sollen definieren und im 'baguetteBox.run' den Namen des Containers uebergeben. (im obigen Beispiel: `gallery )` und den Link auf die großen Bilder setzen.

Vorher hatte ich mal Photswipe probiert , das aber verworfen  da dort mit Javascript Modulen gearbeitet wird und ich mich in das Thema noch nicht reingefuchst hab. desweiteren braucht Photoswipe die genauen Bild abmessungen (width, height) was die Sache beim erstellen von Beiträgen doch erschwert find ich.

[1]: https://feimosi.github.io/baguetteBox.js/
[2]: https://github.com/feimosi/baguetteBox.js/blob/dev/README.md
[3]: https://github.com/feimosi/baguetteBox.js/tree/dev/dist
[4]: https://www.mikyma.de/gehege
[5]: https://www.mikyma.de/vogesen
