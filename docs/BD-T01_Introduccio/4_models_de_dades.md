# **4.Models de dades**
Per a poder definir l'estructura de la B.D. ens farà falta alguna ferramenta, alguna manera d'expressar el que veiem en el món real.

Un **Model de Dades** serà un conjunt de conceptes que poden servir per a descriure, a distints nivells d'abstracció, l'estructura d'una B.D. A aquesta estructura expressada per mig del model de dades l'anomenarem **esquema**. Caldrà diferenciar entre esquema i les dades concretes que pot tenir la B.D. en un moment determinat (a la qual cosa alguns autors anomenen **estat de la B.D.** o conjunt d'**ocurrències** o **exemplars**).

Al llarg de la història s'han proposat molts models de dades, tants que s'hauran de classificar un poc.

- **Models d'alt nivell** o **conceptuals**: disposen de conceptes molt propers a la manera de percebre les dades les persones. El més conegut és el **Model Entitat-Relació**. Uns altres serien els **orientats a objectes**. Serviran per a poder dissenyar la B.D. a partir de les percepcions del món real. Nosaltres veurem el Model Entitat-Relació (M. E/R). El model orientat a objectes està utilitzant-se prou en l'actualitat, bé de forma pura o bé barrejat amb el Model Relacional.
- **Models de baix nivell** o **físics**: proporcionen detalls de com es guardaran les dades a l'ordinador.
- Models de **representació** o **implementació**: estan a mig camí dels dos anteriors, ja que els conceptes els poden entendre els usuaris finals, encara que no estan massa allunyats de la manera com es guarden les dades a l'ordinador. Són els més utilitzats en els SGBD actuals. Es poden destacar el **Jeràrquic**, el **de Xarxa** (o **Codasyl**) i el **Relacional**, que és el que nosaltres veurem en profunditat.

[« Anterior](3_caracterstiques_desitjables_dun_sgbd.md) | [Següent »](5_arquitectura_a_3_nivells.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
