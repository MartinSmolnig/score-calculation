# Score calculation

Sehen wir mal, ob ich richtig verstanden habe, was du machst.  

## was ich glaube, dass du machst
### Normalisierung

Deine Normalisierung berechnet sich wie folgt.  

$$ r=\frac{median_{Rapa}}{median_{MTX}} $$

$$ X'_{Rapa} = \frac{X_{Rapa}}{r} $$

Daraus folgt, dass $X'_{Rapa}$ eigentlich folgendes ist:  

$$ X'_{Rapa} = X_{Rapa} * \frac{median_{MTX}}{median_{Rapa}} $$

Da $ X'_{MTX} $ gleich berechnet wird, ist $ X'_{MTX} $ also:  

$$ X'_{MTX} = X_{MTX} * \frac{median_{MTX}}{median_{Rapa}} $$

Die einzelnen Messwerte werden also mit dem Quotienten der Mediane MTX/Rapa multipliziert.  
An dieser Stelle stellt sich mir die Frage, was denn eigentlich dieser Quotient ist.  
Ich glaube, du hast auch erwähnt, dass du das pro Plattenpaar machst. 
Es gibt also nicht ein $r$, sondern 4?

Sieh dir mal an, wie die Verteilungen der Werte vor der Normalisierung aussehen und wie danach. Ich befürchte, dass die nicht so normalisiert sind, wie du es dir wünscht.  

### Z-score

Aus den _normalisierten_ Werten werden dann die Z-score berechnet.  

Egal ob es sich um einen Rapa oder MTX Wert handelt, verwendest du immer Mittelwert und Standardabweichung von MTX?  
Hab ich das richtig verstanden?

Das wäre dann also: 

$$ Z_{Rapa} = \frac{X'_{Rapa}-\mu_{MTX}}{\sigma_{MTX}}$$

bzw.  

$$ Z_{MTX} = \frac{X'_{MTX}-\mu_{MTX}}{\sigma_{MTX}}$$


## mein Vorschlag

Die Normalisierung erscheint mir fragwürdig.  

Versuche mal, das hier.  

$$ Z_{Rapa} = \frac{X_{Rapa}-\mu_{Rapa}}{\sigma_{Rapa}}$$

bzw.  

$$ Z_{MTX} = \frac{X_{MTX}-\mu_{MTX}}{\sigma_{MTX}}$$


Darauf folgend ...  

$$ Z_{ratio} = \frac{Z_{Rapa}}{Z_{MTX}} $$

Ich glaube, dass das deine Abhängigkeit der Proteinhäufigkeit eher in den Griff kriegt.

Mit den $Z_{ratio}$ Werten kannst du dann in die Statistik und GO etc. gehen.

