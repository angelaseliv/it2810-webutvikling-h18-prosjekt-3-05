# it2810-webutvikling-h18-prosjekt-3-05

## Personal Information and Motivation Manager
Personal Information and Motivation Manager er en app som lar en bruker opprette ulike mål, med tilhørende Todo-lister for hvordan målet kan oppnås. I tillegg følger det med en skritteller slik at brukeren kan tracke antall skritt den går. 

### Tutorials how to use this amazing app
npm install
npm i react-native-paper

## About React Native
React Native er et rammeverk som generer "real mobile app" fra JavaScript for flere plattformer istedenfor en hybrid med web view. React Native lar deg lage en mobilapp ved hjelp av JavaScript og React-biblioteket. En av de største fordelene med Native er at den har delt kodebase for iOS og Android. Siden rammeverket er ekstremt populært så støtter det en rekke forskjellige plugins og trdejepartsbibliotek for å utvide funskjonalitetmulgheter til appen din. Det gir utvikleren en bred spekter av løsningsmuligheter.
React Native har mange innebygde komponenter som er lett å ta i bruk. For exempel <View>- komponentet er brukt for å vise inneholdet på skjermen.

### Why Native? (den skal mest sannsynlig slettes, har den bare for å lære noe selv og just in case)
A native mobile app is a smartphone application that is coded in a specific programming language, such as Objective C for iOS or Java for Android operating systems. Native mobile apps provide fast performance and a high degree of reliability. They also have access to a phone's various devices, such as its camera and address book.

## Third-party-libraries and Tools
### * [Expo](https://expo.io/)
Expo er et verktøysett som hjelper å utvikle en app uansett platform. Fordelene er at man kobler til gjennom wi-fi og slipper å bruke USB som i lokal bygging av app og at applikasjonen blir oppdatert umiddelbart etter man lagrer endringer.

### * [React Native Paper](https://callstack.github.io/react-native-paper/index.html)
Dette biblioteket tilbyr godt utformet Material Design-klare designkomponenter som fungerer og ser ut nesten likt både på iOS og Android. Komponenter har en universiell utforming som er intuitive for brukeren å ta i bruk og er ment å hjelpe å skape gode brukeropplevelser.  

### * [Expo Pedometer](https://docs.expo.io/versions/latest/sdk/pedometer)  
Expo has an example implementation of a pedometer that uses Core Motion (iOS) and Google Fit (Android) to get the user's step count. Using this method we were able to get the step count on both operating systems, except for one issue that occurs when reloading the expo client, this error is however caused by expo not running the componentWillUnmount() function upon reload. The user will not be signed out from the GoogleApiClient and upon sign-in the error "Already managing a GoogleApiClient with id 0" will pop-up. This will not be a problem in production.  

- react-navigation library why and how

## Layout
Bruker Flexbox da den rangerer/ plasserer elementer i forhold til hverandre.

## Storage
Fordi ingenting av det vi lagrer er sensitive data, trengs det ingen kryptering, og derfor er AsyncStore flott å bruke. I tillegg er AsyncStorage laget slik at data lagres på enheten mellom hver gang appen kjører. Det vil si at hver unike bruker av appen kan lagre og hente sin egne unike data i appen. Både goals, skrittellingsinformasjon og todo-listene blir lagret med AsyncStorage. AsyncStorage er lett å bruke, og man lagrer elementer enkelt ved å bruke setItem(key,value)-funksjonen. Man kan deretter hente frem elementene igjen ved å kalle på getItem(key)-funksjonen.

## Testing
Testing har vært en vitkig del i utviklingsprosessen av appen vår. I starten testet vi for det meste på mobil, for å se at komponentene fungerte som de skulle i appen og for å se hvordan stylingen og plasseringen av elementene ble. Etter hvert som komponentene ble ferdig, begynte vi å teste dem med Jest.

### Jest
Jest er utviklet for å teste all JavaScript-kode inkludert React. Det er relativt lett å skrive i, da syntaxen ligger tett opp mot det engelske språket.

Én av våre hovedutfordringer da vi testet med Jest, var at Jest ikke kan teste endringer i state og trigging av funksjoner i parent- eller childkomponenter. Fordi de fleste av våre funksjoner enten oppdaterer state eller kaller funksjoner i andre komponenter, har vi måttet benytte oss av flere mock-funksjoner. Istedenfor å teste endring i state, har vi valgt å teste at setState-funksjonene blir kalt. Det samme gjelder kall på funksjoner i andre komponenter. Også her har vi valgt å sjekke at rett funksjon blir kalt, heller enn å sjekke resultatet av funksjonskallet.

En annen utfordring vi støtte på, var at ikke alle komponentene våre ville rendre da vi testet dem. Dette gjelder HomeScreen og CreateGoalsScreen. Fordi komponentene ikke har villet rendre i Jest, har vi heller ikke hatt mulighet til å teste funksjonene i komponentene . Vi mener likevel at vi har vist at vi har vist at vi kan bruke Jest til testing, gjennom å teste grundig i de komponentene vi har fått til å rendre. Blant annet TodosScreen og TodoList mener vi er godt og grundig testet.

Ideelt sett skulle vi aller helst ha fått testet alle komponentene i appen vår med Jest, men etter å ha brukt utallige timer på å finne en løsning på renderproblemene våre, både vha Google, Blackboard, studasser og andre medstudenter, måtte vi til slutt innfinne oss med at vi ikke har fått til å teste alt med Jest.

### Testing on Android and iOS devices
I utvikling av prosjektet hadde vi 2 iOS-enheter(iPhoneSE og iPhone6) og en Android(OnePlus 6). Siden vi alltid kjørte Expo ved utvikling av appen fikk vi testet nylig lagt funskjonalitet fortløpende.

For å teste appen ytterligere, har vi også bedt andre studenter om å kjøre appen på sin telefon og komme med tilbakemeldinger. På denne måten fikk vi testet appen vår på flere plattformer, i tillegg til at vi oppdaget enkelte utfordringer knyttet til brukeropplevelsen, som vi har forsøkt å forbedre etter beste evne.

Vi har hatt ekstra fokus på å brukerteste det vi ikke har fått testet i Jest, for å avdekke alle potensielle feil. Derfor mener vi at vi har testet appen vår grundig og systematisk.

## How we used Git
I dette prosjektet har vi hatt ekstra fokus på å bruke git aktivt. Vi har benyttet oss av både issues og prosjekttavlen. Vi har merket commits med issues og flyttet issues'ene på prosjekttavlen etter hvert som vi har startet og fullført et issue.
De fleste issues har blitt fordelt på én eller flere av gruppas medlemmer slik at vi har hatt oversikt over hvem som har jobbet med hva.

## Sources
* [Your next React Native app will be done with Paper](https://blog.callstack.io/your-next-react-native-app-will-be-done-with-paper-40eebd88be98)
* [Jest Mock AsyncStorage for react-native](https://www.npmjs.com/package/mock-async-storage)
* [Testing React Native Apps](https://jestjs.io/docs/en/tutorial-react-native)
* [Testing React Apps](https://jestjs.io/docs/en/tutorial-react)
* [Snapshot Testing](https://jestjs.io/docs/en/snapshot-testing)
* [Mock Functions](https://jestjs.io/docs/en/mock-functions)
* [TodoList part 1](https://blog.eduonix.com/mobile-programming/learn-build-react-native-todo-application-part-1/)
* [TodoList part 2](https://blog.eduonix.com/mobile-programming/learn-build-react-native-todo-application-part-2/)
* [TodoList part3](https://blog.eduonix.com/mobile-programming/learn-build-react-native-todo-application-part-3/)
* [Icons](https://expo.github.io/vector-icons/)
* [How to make your React Native app respond gracefully when the keyboard pops up](https://medium.freecodecamp.org/how-to-make-your-react-native-app-respond-gracefully-when-the-keyboard-pops-up-7442c1535580)
