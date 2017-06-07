---
layout: post
title:  "Arch Linux yaourt e lo spazio finito su disco"
date:   2017-06-07 21:44:32
categories: [how-to, linux, arch linux, tmp, yaourt]
---
È da tanto non scrivo, anzi a dire la verità non ho quasi scritto su questo mio blog. 

Ultimamente mi è passata per la testa l'idea di riprenderlo e iniziare ad essere leggermente costante nel pubblicare post.

Quindi questa sera ricomincio a scrivere, rinizio condividendo con voi la soluzione ad un problema che ho dovuto affrontare in questi giorni.

Chi mi conosce sa che amo Arch Linux, mi piace la sua semplicità ed il suo essere spoglio.
Mi piace il fatto di avere pieno controllo sul mio sistema.

Proprio questo fatto di avere pieno controllo del proprio sistema a volte può essere un arma a doppio taglio, soprattutto se non si è del tutto esperti.

Il problema di cui vi voglio parlare si può presentare mentre installate un pacchetto con yaourt o se il software che usate necessita di scrivere grossi file nella vostra directory temporanea. Su Arch Linux bisogna sapere che la directory _"/tmp"_ sarà sempre la meta della ram installata nella macchina su cui gira.

Nel primo caso, ovvero durante l'installazione di un pachetto tramite yaourt che restituisce un bel: _"out of space"_.
Una soluzione potrebbe essere la seguente:

`
mkdir ~/.newtmp
export TMPDIR="/home/$USER/.newtmp"
`

questo spostera temporaneamente per la sessione della shell corrente nella home la vostra directory _"/tmp"_, ricordatevi di cancellare la cartella per rimuovere i file temporanei altrimenti resteranno lì.

Il secondo metodo funziona anche all'esterno della sessione shell in cui lanciate il comando, quindi si presta bene nel caso in cui un software che necessita di creare grossi file temporanei vi dice che non c'è più spazio.
(Io ho usato questa solouzione per installare tutti gli SDK Android che necessitavo, sono davvero un sacco di GB :| )
Comunque il comando è il seguente:

`mount -o remount,size=10G,noatime /tmp`

una volta lanciato questo comando la nostra cartella _"/tmp"_ passerà dalla metà della ram a 10GB, ricordate che la dimensione risulterà cambiata fino al prossimo boot.
