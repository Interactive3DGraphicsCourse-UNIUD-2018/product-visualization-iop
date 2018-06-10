# JOURNAL DI PROGETTO - Turus Davide, Iop Alessandro
## 14/05/2018
- Spartizione del lavoro da fare all'interno del progetto.
- Abbiamo optato per la creazione di una pagina web completa in tutti i suoi aspetti (quindi quasi pronta per il deployment) ma non interagibile al di fuori del contesto di progetto.
- I link eventuali dell'header, del menu, del footer e di acquisto del prodotto saranno disattivati.
- Per una questione di semplicità nella gestione dell'interazione dell'utente, non saranno presenti elementi di input di tipo testuale (e.g. `<input type="text">`), neanche in contesto di progetto.
- Gli elementi di interazione, come indicato nella consegna del progetto, saranno interamente realizzati tramite elementi html e non tramite librerie di three.js per la GUI, a eccezion fatta per i controlli orbitali del prodotto e lo zoom sullo stesso.
- A seconda del prodotto presentato, l'idea generale è quella di permettere all'utente di selezionare diversi tipi di materiali, il colore della luce, diversi sfondi, abilitare l'environment map e/o attivare il fullscreen.
- La soluzione proposta per l'illuminazione della scena è quella di utilizzare due spot lights e un'eventuale environment map.
- Abbiamo deciso di seguire l'opzione b al punto 7 della consegna, cioè scrivere gli shader da capo a partire da quelli visti a lezione.

## 18/05/2018
- Inizio costruzione della pagina web statica, aiutandosi con un esercizio completo già visto a lezione.
- Costruzione di una shell vuota seguendo i dettami di html5, con un header, un nav e un footer.
- Per il menu di navigazione abbiamo optato per poche voci che più frequentemente possono essere trovare su un sito di e-commerce: home, carrello, i prodotti e area personale.
- L'area personale consiste a sua volta di un menu a tendina con voci anch'esse comuni come: log in/sign in, il mio account, i miei ordini, privacy.
- Per simulare efficacemente un sito di e-commerce che vende memorabilia di film della Marvel (il nostro modello 3d è uno di essi), ma per evitare di commettere violazioni di copyrights, il logo della Marvel e alcuni altri nomi ben noti ad essa collegati sono stati volutamente modificati.
- Tutti i link ipertestuali presenti nella pagina sono vuoti, cioè non reindirizzano a nessun'altra.

## 23/05/2018
- Inserimento primi contenuti nella pagina statica e regolazione dell'aspetto generale mediante css: logo Marvel modificato con gimp, titolo e sottotitolo del prodotto, prezzo, descrizione testuale e bottone di inserimento dello stesso nel carrello.
- Il tema della pagina è semplice ma omogeneo: i colori scelti fanno chiaramente riferimento a quelli di Iron Man, siccome il prodotto che si vuole vendere è legato a tale saga cinematografica.
- Non essendo semplice la regolazione delle dimensioni e il rapporto d'aspetto della canvas nel modello 3d, oltre al fatto che quello usato per il testing è provvisiorio, essa è stata lasciata alle dimensioni di default e posizionata al centro del corpo principale della pagina; c'è però la possibilità che possa risultare troppo piccola di dimensioni.

## 29/05/2018
- Aggiunta nel footer di un baner informativo oltre al già presente bottone "torna su"; tale banner conterrà gli indirizzi mail dei componenti del gruppo (funzionanti), contenuti graficamente in una sezione "Contattaci" delimitata da bordi verticali separatori.
- Integrazione delle icone trovate su theNounProject nel menu di navigazione (non i quello a tendina) e nel bottone di inserimento del prodotto nel carrello.
- Inserimento all'interno del footer dei credits alle icone, per non tenerli sotto alle icone stesse e quindi ripetuti 5 volte; si tratta di motivi più che altro estetici, giustificati anche dalle istruzioni trovate sul sito di theNounProject su come scrivere correttamente i credits.
- Le icone sono in formato svg, per cancellare i credits in esse integrati basta eliminare parte del codice svg (che è mantenuto come file esterno), per cambiare invece il colore del disegno non si è ancora trovata una soluzione; ci si è risolti quindi a mantenere le icone al nero originale, poiché inserite in elementi del DOM con sfondi bianchi, e regolare l'aspetto del bottone di inserimento nel carrello di conseguenza.
- Per la regolazione dell'aspetto delle icone prima di inserirle nella pagina è opportuno inoltre ricordare di impostarne lo sfondo a trasparente (tramite css) e di regolarne la dimensione, cioè "ritagliarle", modificando l'attributo viewBox del tag svg nel file originale.
- La gui originale dell'esercizio visto in classe è stata mantenuta nel progetto provvisoriamente perché occupa più o meno l'area che occuperanno i controlli in input che l'utente potrà regolare sul modello 3d.

## 01/06/2018
- Lo sviluppo della parte riguardante il rendering del modello scelto è iniziato costruendo uno shader di base che consenta un calcolo della luce di due pointLight e la computazione tramite texture dei termini speculare e diffusivo, della roughness e delle normali.
- La scelta per la BRDF è ricaduta su una combinazione di calcolo del termine diffuse e di un Microfacet in modo da tenere in considerazione sia il termine speculare che quello diffusivo.
- Le texture fin'ora utilizzate sono quelle fornite con gli esempi del corso.

## 02/06/2018
- Risolto un problema direvante dall'utilizzo della normal mapping per la perturbazione delle normali tramite modifica del codice adattando quindi il codice dell'esercizio eseguito in classe.
- Viene aggiunta una ambient light alla scena e le texture dell'ambient occlusion dei materiali per avere una prova del funzionamento del codice, l'ambient light verrà in seguito sostituita dalla environment light al momento dell'inserimento della environment map.
- Lo shader è ancora applicato a tutto il modello e non ai singoli elementi per motivi di semplicità nella verifica del corretto funzionamento del codice.

## 03/06/2018
- Cambiato il typeface della pagina, l'intenzione è di mantenerne uno sans-serif con una buona spaziatura tra caratteri e un aspetto distinto, che sia facilmente leggibile e adatto ai contenuti per il web.
- Oltre al nome della Marvel, per evitare violazioni di copyrights abbiamo sostituito con nomi fittizi anche quelli del prodotto da vendere (originariamente Arc), dei personaggi menzionati, degli Avengers e della saga cinematografica di Iron Man.
- La larghezza del testo descrittivo posto a seguito del modello 3d è stata ridotta al fine di "fare volume" e allinearla alla griglia immaginaria imposta dai margini della canvas soprastante; un'idea potrebbe essere quella di disporre i controlli per il modello in modo che spazino lungo tutta la larghezza del corpo centrale e non solo quella della canvas; in tal modo si manterrebbe un layout essenziale e uniforme ma non troppo "compresso".
- Il bottone di aggiunta al carrello e il prezzo del prodotto da vendere sono stati spostati entrambi sulla destra, ma la loro posizione potrebbe essere ulteriormente aggiornata, per simulare quelli che sono i più popolari siti di e-commerce in circolazione.
- L'aspetto del suddetto bottone è stato regolato in modo che sia in linea con il resto del tema della pagina web, ma è stata anche fornita un'affordance che faccia capire all'utente che tale bottone è interagibile, sotto forma di ingrandimento al passaggio del puntatore sul bottone stesso; essendo infatti dotato solo di bordi colorati, potrebbe essere scambiato per un semplice riquadro contente informazioni, anche se il testo dice chiaramente "aggiungi al carrello".
- Per "decomprimere" il contenuto della pagina, quindi per aggiungere più spazio tra un elemento del DOM e l'altro, sono state regolare anche le spaziature tra essi nel css (spesso tramite l'attributo margin-bottom).
- Anche l'aspetto del bottone "torna su" è stato regolato, ma potrebbe essere cambiato ulteriormente sia in forma che in colore perché non sembra essere del tutto soddisfacente.
- Nello shader viene aggiunto il calcolo della environment light derivata dalla cube map applicata, temporaneamente si utilizza quella fornita con gli esempi. Per il calcolo della environment light si utilizza il metodo visto a lezione cioè sfruttare le mipmap al livello utile per il materiale al posto della IEM.
- Rimane il problema dell'assenza di una texture dell'ambient occlusion a livello generale del modello perché non si riesce ancora ad ottenerla da un file gltf tramite i programmi utilizzati.
- Aggiunta di un pavimento provvisorio per verificarne l'effetto grafico.

## 04/06/2018
- Regolata tutta la responsiveness della pagina per gli elementi presenti finora, manca infatti la componente di interazione dell'utente con il modello 3d: è stato necessario mettere più tresholds del previsto, in quanto diversi elementi di tipo testuale (menu di navigazione, testo descrittivo, contenuti del footer) andavano a capo in punti diversi; sono stati talvolta anche ridisposti del tutto alcuni elementi per adattarsi al meglio alle proprietà dei display più piccoli.
- Il bottone "torna su" è da abbellire, ed è da gestirne il posizionamento una volta che la pagina è stata scrollata fino in fondo, in modo che il contenuto del footer sia sempre leggibile; una proposta sarebbe quella di un meccanismo simile al menu "sticky", ma verso il basso.
- Nel caso dei display più piccoli, un testo descrittivo giustificato risulta troppo spaziato e dispersivo, per questo oltre la soglia dei 545px è allineato a sinistra.
- Anche il modello 3d è stato regolato di dimensioni nella parte della responsiveness, passa infatti dall'essere metà delle dimensioni della finestra ai rispettivi 9/10 una volta raggiunta la soglia dei 715px di larghezza: il cambiamento delle dimensioni è effettivo solo tramite un refresh della pagina dopo averla ristretta/allargata, ma per noi non costituisce un grande problema perché nella maggior parte dei casi si tratterà in primo luogo di caricare la pagina direttamente su schermi piccoli, e raramente sarebbe necessario per l'utente restringere la finestra così tanto da compromettere l'usabilità dell'applicazione.
- Rimozione dell'ambient light in modo da utilizzare la environment light derivata dalla cube map come fonte di luce per l'ambient occlusion.

## 05/06/2018
- Viene creata una funzione che permette di applicare il materiale desiderato al frammento del modello desiderato.
- Tramite l'ausilio di Blender si provvede alla generazione di un modello unico in formato FBX dalla scena formato GLTF, si prosegue alla creazione di una normal map e una ambient occlusion map totali dell'oggetto tramite il programma Substance Designer.

## 06/06/2018
- Per la personalizzazione dell'oggetto da parte dell'utente, i controlli scelti sono sul materiale presentato sotto forma di `<button>`, sul colore della luce (rossa, blu, verde, bianca) presentata sotto forma di `<input type="radio">`, sulla componente dell'oggetto correntemente in fase di personalizzazione (sostegno, anello interno, anello esterno...) presentata sotto forma di `<select>`, sullo sfondo (bianco/senza environment map, multiple abientazioni d'interno/con environment map) presentato sotto forma di `<button>`.
- Per questioni di tempo e di estetica nel layout della pagina, ci riserviamo all'ultimo la decisione di aggiungere o meno l'opzione fulllscreen, che si presenterebbe sotto forma di `<input type="checkbox">`.
- L'interazione con l'interfaccia di personalizzazione dell'utente sarà gestita in maniera asincrona in javascript alla stessa maniera della gui predefinita di three.js; la chiamata alla funzione di update avverrà direttamente dagli elementi del DOM con cui sarà avvenuta l'interazione, e i parametri passati in tali occasioni identificheranno sia l'attributo del modello 3d da modificare che i valori di tale attributo nel dettaglio (ad esempio il nome della texture da caricare o dell'environment map da mettere come sfondo).
- E' stato risolto un problema di clipping del testo nel menu di navigazione della pagina web che impediva la corretta visualizzazione delle voci all'interno di Google Chrome (che è un browser non-webkit).
- Per quanto riguarda una disposizione ordinata, semplice e bilanciata degli elementi del DOM nella parte dedicata all'iterazione dell'utente, l'idea è di inserire sulla sinistra 6 piccoli bottoni delle texture, al di sotto del menù a tendina in cui si potrà scegliere la componente del modello per cui si vogliono applicare le texture. Al centro una lista di radio buttons per la selezione del colore della luce separeranno i bottoni di sinistra con gli altri 4 bottoni per la selezione dello sfondo, che saranno posti sulla destra. Essendo più grandi dei primi, i secondi occuperanno grossomodo lo stesso spazio loro considerando anche quello occupato dal menù a tendina soprastante.

## 08/06/2018
- Per la personalizzazione è stata creata una funzione di update che gestisca i parametri inseriti dall'utente e aggiorni il materiale in base a questi
- Per i materiali sprovvisti di diffuse e specular ma gestiti con baseColor e metalness è stato creato uno shader apposito
- Nel caso di sfondo bianco al posto dello shader che calcola la luce ambientale dalla envmap è stato creato uno shader che utilizza una ambient light generica prefissata anche se questa scelta prevede una sovrastima della luce

## 10/06/2018
- Sono stati scaricati dei materiali e gli shader corretti ove serviva, purtroppo è stato riscontrato un problema sul modello che provoca una riflessione speculare in alcuni punti anche se il materiale non la presenta.
- Regolata la responsiveness del menu di personalizzazione del prodotto, e ultimata la descrizione sottostante.
- La funzione di update viene ora chiamata solo quando viene cliccato un bottone di texture/sfondo o un radio button, non quando si seleziona dalla tendina; tramite una variabile globale, al momento dell'onchange() del tag `<select>`, si "salva" il nome del componente dell'oggetto 3d sul quale andranno poi fatti gli eventuali aggiornamenti di texture.
- L'integrazione del prototipo scritto nel file "progetto.html" nella pagina "index.html" non è stata senza sofferenze: inizialmente sono stat riscontrati problemi nella personalizzazione del prodotto sotto quasi tutti i punti di vista, successivamente nella gestione dei casi particolari di interazione e infine nell'apertura della pagina direttamente da browser (senza web server locale). Ci siamo risolti infine a utilizzare il server locale, in quanto su alcuni browser non è possibile accedere ai media presenti nel file system necessari al funzionamento dell'applicazione.
- Per quanto riguarda gli sfondi, mentre quelli rappresentanti interni sono frutto di environment maps derivate da cube maps, quello bianco è gestito con una semplice ambient light.