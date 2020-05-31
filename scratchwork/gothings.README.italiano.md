# Il progetto GOTHINGS

Usando insieme docker, schede raspberry ed applicazioni cloud: Docker Distributed Things
<br />  

----
<br />

AVVISO:
----  

**Questo progetto è in costruzione.**  

La documentazione di questo progetto è scarsa e non affidabile, a causa della (ri-)definizione in corso di molti aspetti secondari del progetto.
A causa di quanto sopra, tieni presente che potrebbe essere quasi impossibile utilizzare questo repository per fare qualsiasi lavoro utile.

Ad ogni modo, il lavoro originale qui incluso può essere utilizzato secondo la permissiva Licenza MIT.

<br />  

----

[Cosa puoi trovare qui](./gothings.README.italiano.md#cosa-puoi-trovare-qui)  
[L'Inizio](./gothings.README.italiano.md#l-inizio)  
[INDICE](./gothings.README.italiano.md#indice)  
[Stato di avanzamento](./gothings.README.italiano.md#stato-di-avanzamento)  
[AVVERTENZA](./gothings.README.italiano.md#disclaimer)  
  
<br />  
----

Cosa puoi trovare qui
----

Scenario
* oggetti internet realizzati con schede embedded come le raspberry
* un sistema di gestione per oggetti internet
* un modo di usare insieme macchine cloud e cose internet
* -- Questa lista e' da completare --
  
<br />  
----

L'Inizio
----
  
**Internet of Things** o [IoT](https://en.wikipedia.org/wiki/Internet_of_things) indica un insieme di tecnologie che permettono di realizzare oggetti capaci di comunicare tra loro, usando anche l'internet degli esseri umani, senza il loro intervento diretto.  
Ho avuto modo di partecipare ai primi sviluppi assieme a collaboratori e discutendone con gli studenti nel corso di Telematica.  
Successivamente, diminuiti gli impegni di lavoro, ho continuato ad occuparmene cercando una astrazione con la quale inserire le tecnologie IoT in una visione strategica piu' allargata.  
  
Penso di poter meglio illustrare  il mio pensiero esponendolo attraverso una immaginaria discussione con me stesso, che riporto sotto.  
  
Mi faccio una domanda semplice:  
* Cosa mi serve per sapere quanta elettricita' ha consumato oggi la mia casa?.  
In un mondo perfetto la risposta e':  
* ...dato che ho una infrastruttura IoT perfetta, guardo il dato direttamente sul mio telefonino.  
In effetti, basta che nella mia casa sia installato un dispositivo che prende il dato dal mio impianto elettrico (esiste e costa meno di 30 Euro), lo espone tramite wifi (qui andiamo peggio) ed ho installato sul mio telefonino una app che mi mostra il dato.  
A parte il lettore di potenza attiva, il resto e' praticamente a costo zero.
  
Vediamo cosa succede nel mondo reale:  
* e' semplice: compro Amazon Alexa o Google Home o Apple Homekit
* scelgo sul mercato un dispositivo che svolga la funzione che mi serve
* il costruttore del dispositivo ha realizzato uno *skill* alexa (o simile)
* alexa (o il concorrente) mi fornisce il risultato
  
FUNZIONA?
- humm... SI, quasi
- intanto, ho speso un mucchio di soldi per uno dei sistemi *home*
- non e' facile selezionare il dispositivo e installarlo e' complicato
- perche' devo chiedere un dispositivo *compatibile*?
- il risultato e' a *scatola chiusa*, o cosi' o niente
- perche' uso il mio browser su tutti i siti ma non riesco ad usare il dato dei consumi in altre applicazioni?

Quale problema tecnico esiste?  
  
Vediamo: per fare una cosa semplice, come mostrare un dato fornito da una cosa, devono funzionare una serie di servizi elementari che riguardano la cattura del dato, la trasmissione di esso ad una memoria interna (sara' un database) la trasmissione dalla memoria ad un dispositivo di visualizzazione (in molti casi un telefonino) una app presente sul dispositivo che consente al proprietario di chiedere e quindi di vedere il dato.  
Il tutto dovrebbe funzionare con almeno un minimo livello di sicurezza, dato che mi disturberebbe che le luci di casa mia venissero accese o spente da un passante qualsiasi ...  
Dovrei avere disponibile uno storico dei consumi e dovrei poterlo trasferire in un foglio di calcolo ...  
Dovrei poter usare i miei dati in qualunque modo mi venga in mente ...  

Allora, come risolvo il problema?  

Risposta attuale: e' necessario avere una grande impresa che abbia la capacita' di organizzare il tutto.  
Una grande impresa puo' dire ai produttori di sensori come devono costruirli, quale protocollo usare per trasmettere il dato, con quale formato memorizzarlo nel loro database, e cosi' via.  
Solo una grande impresa puo' costruire una applicazione *giusta* per far vedere agli utenti i dati nel formato che loro vogliono, solo la grande impresa ha la potenza di calcolo necessaria per *vedere* nel mare dei dati tendenze latenti per poi meglio servire i propri clienti, solo la grande impresa puo' offrire la sicurezza di trattare correttamente i miei dati, solo la grande impresa ...  
  
OOPS!  
E' la strada giusta?  
  
Quanto sopra mi ricorda una domanda posta ad una lezione di Telematica nel 1993, la domanda era:
 * Cosa mi serve per far funzionare un foglio elettronico sul mio PC?
   
  La risposta era (al 95% o forse piu'):
 *  non mi serve NIENTE, mi basta usare il programma Microsoft Excel sul mio computer Windows  
   
 In sostanza: un bel Sistema Operativo risolve ogni problema, quindi possiamo affermare che manca un sistema operativo per le cose che faccia quello che ha fatto MS Windows per il PC  
Pero' sarebbe meglio che il sistema operativo prendesse piu' da Linux che non da Windows. 
 
 NOTA: puoi trovare una discussione sul [sistema operativo](./gothings.README.italiano.md#dettagli-il-sistema-operativo-tradizionale) piu' avanti  
  
L'inconveniente principale di un OS e' che la presenza di una grande impresa puo' portare problemi di dipendenza e molto altro.  
Allora, vediamo: posso sostituire la grande impresa con lo stato nazionale?  
... con l'Europa?  
... con l'ONU?  
  
La mia risposta e':  NO!  
Le grandi organizzazioni (**TUTTE**, siano esse politiche, religiose, imprese o stati sovrani) hanno la tendenza a creare monopoli, a uccidere l'evoluzione tecnologica, ed alla fine trasformare tutto in vantaggi per i propri membri a discapito di tutto il resto dell'umanita'.  

Quale strada suggerisco?  
**Rispondere al pattern 'grande impresa' (o grande fratello), con il pattern LINUX**.  
  
  
<br />  
----

Sviluppo di GOTHINGS
----

Cosa sarebbe ideale:
1.- partire da un sistema il piu' vicino a quello che serve;
2.- eliminare gli ostacoli legali rendendo tutto di pubblico dominio
3.- partizionare il problema tecnico in sottosistemi efficaci
4.- per ogni parte preoccuparsi prima degli sviluppatori, poi degli utenti
     * su questo possiamo aprire una lunga discussione e discutere di startup e imprese innovative
     * possiamo includere personaggi fai-da-te, come:
            * [Richard_Stallman](https://it.wikipedia.org/wiki/Richard_Stallman)
            *  [Linus Torvalds](https://it.wikipedia.org/wiki/Linus_Torvalds)
            * [Tim Berners Lee](https://it.wikipedia.org/wiki/Tim_Berners-Lee)
     * ed includere nel mix un mucchio di hobbisti e professionisti del software *open sopurce*
5.- porre estrema attenzione nel rendere il sistema globalmente migliorabile attraverso aggiustamenti incrementali in ogni parte in modo indipendente dalle altre
6.- usare SEMPRE standard non proprietari in alternativa: un pattern che consenta di integrare tecnologie proprietarie, ma che consenta la loro facile sostituzione senza disturbo al resto del sistema
  
DIRETTIVE
- pretotipare ogni cosa
     - nota: [pretotipare]() non e' un refuso
     - puoi [comprarlo](https://www.amazon.it/Pretotype-Pretotipare-Assicurati-costruirela-costruirla/dp/1481881736)
     - trovare una [breve introduzione](https://www.lascianca.it/come-trasformare-unidea-in-una-cosa-vera/) al concetto
     - fare un [download](https://www.escogita.org/download/66/in-questa-sezione-e-possibile-trovare-una-raccolta-di-strumenti/802/pretotype-it-pretotipare.pdf) in formato .pdf
- piattaforma hardware libera e poco costosa;
- piattaforma software libera
- componenti software piccoli e 'mono-obiettivo'
- comunicazione HTTP per tutto
  - eventualmente, adapter tra comunicazione proprietaria e HTTP
- definire API per tutti i servizi
- cos'altro manca?

  
  
<br />  
----

Un primo tentativo.
----

Visto che per ora sono solo io, scelgo cose semplici:
- Rasperry + raspbian linux
- Docker containers per ogni macrofunzione
- Sottosistema per la configurazione ed installazione di una base minima
  di servizi necessari
- strati applicativi specifici per macrofunzioni necessarie
  esempi: securizzazione delle comunicazioni, database locale, ...


Struttura di GOTHINGS

L'elemento base e' il contenitore Docker.
Esso contiene/realizza un servizio essenziale per il sistema
GoThings e' quindi un insieme di contenitori cooperanti.

Osservazione tecnica.
Se la comunicazione e' http, ovvero se l'iniziatore definisce e raggiunge il corrispondente tramite un URL, la collocazione del particolare container su un particolare host od un altro non ha importanza  
  --> in linea di principio e' corretto, in pratica influenza molti dettagli operativi

Si parte definendo cio' che deve stare dentro un host che chiameremo 'gateway'
  --> a gateway is:  'an opening that can be closed by a gate'
Il nome e' indicativo del fatto che prevediamo una architettura logica in cui si possa
definire un 'interno' e, conseguentemente, un 'mondo esterno'
L'esempio piu' eclatante e' il cosiddetto 'home gateway', posto tra la LAN di una casa e
l'internet pubblica

In GoThings il gateway e' l'interfaccia tra tutti i contenitori interni ed internet
  --> una qualunque comunicazione e' 'interna' per la parte tra il gateway e
      una cosa appartenente al sistema in oggetto
  --> una comunicazione e' 'esterna' o 'pubblica' per la parte dal gateway al
      resto di internet
  --> chiameremo 'locali' i servizi e le cose appartenenti al sottoinsieme di interesse
  --> e' da osservare che internet prevede, salvo rare eccezioni, che una LAN sia
      interfacciata ad internet attraverso un unico elemento (il router)

Nel gateway porremo un insieme 'base' di contenitori e, eventualmente, altri contenitori
che chiameremo 'user'

La parte BASE contiene, al minimo:
- un proxy HTTP/s (nginx) che gestisce le chiamate verso i contenitori interni
- un database key/value (redis) che mantiene sia dati di sistema che dati operativi
  dai vari contenitori
- un raccoglitore degli eventi interni al gateway (logspout)
- un server di eventi che raccoglie gli eventi locali, sia interni all'host che
  provenienti dalle varie cose interne  
<br />  
----

INDICE
----
 (attualmente un server nodejs con interfaccia UDP)
- si prevede anche un secondo server nodejs per la gestione della sicurezza, il
  pretotipo e' basato su VUE





------------------------
la distanza tra tutto cio' che ci vuole per fare la cosa semplice e quanto offre il sistema base e' troppo grande


-----------------------
TEST di verifica per la buona strada:

Si riesce ad usare una libreria raspberry per avere un valore 'utente' ed a mostrarlo su una pagina web SENZA conoscere nessun comando docker e SENZA dover installare un proprio server web

----
**TO BE CONTINUED**
....  
  
<br />  
----

INDICE
----

The following repos are defined:
* gothings-install
      * Installation of Docker Distributed Things on the raspberry 
* a way to manage a number of things in private LAN
* a way to manage  a number of droplet in your cloud
* -- this list: TO-BE-ADJUSTED


<br />
  
# AVVERTENZA

----

As commonplace in github, the project may include other work which may have different licensing terms.  
The author make his best to note usability and provenience of every work included here.  

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
   
<br />  
----

# DETTAGLI
   
<br />  
----

DETTAGLI: Chi controlla i miei dati?

* in via di sviluppo  
discussione sui formati proprietari  
controllo del produttore sul funzionamento del software
siamo sicuri che non esista uno switch per spegnere il nostro telefonino?





