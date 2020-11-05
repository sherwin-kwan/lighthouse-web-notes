## Day 39 - 5 Nov 2020

## Class-Based React

* Historically, React components were declared using classes in Javascript (function components are a newer way)
* You would create a class that *extends* the class React.Component
* Class-based components can only have a single state. (Unlike with hooks/functions where you can call useState a few times); instead, you create a state object with key-value pairs to have multiple kinds of state
* the render() method of each class causes the component to appear, and it is called on every variable change. A single instance of the class is created on page load, and the render runs again and again. (As opposed to a function, where the *entire* function is run every time a re-render is needed)

## Some Differences 

* In class-based components, stale state is less of an issue. You can call *this.state* anywhere within a class and get the most up-to-date state
* However, there can be issues with the use of the keyword *this*. If you create a function change() for example, and use *this* within that function intending to refer to the class, it's only going to work if you call change() with an arrow function (which preserves the original *this* context)
* Use *componentDidMount* (function that runs when a component first loads) and *componentDidUpdate* to update states. You will need to fetch and change the data on mount, and then re-render on update. These are equivalent to using useEffect and similar hooks in function-based React.
* *componentWillUnmount* is used for cleanup

## Travis's Tips

* Fiber: the algorithm that makes React tick, builds shadow DOM, etc.
* If having trouble with *this*, bind *this* explicitly

## List of Employers

Ad Auris
ADZV
Agency 5 Inc.
Art & Science
Arternal
ATG Pharma
BEEM
BeResponsive
Blue Door Support Services
Brave Technology Coop
Brickspace Lab
BrokerBay
Bubblebox
Commercial Xclusive Inc
Consilium Crypto
Delfs' Engineering
Dig Insights / Upsiide
Dylan Chernick
Eden
elecsoft
Éphémère Creative
EQ Works
FlipGive
GeoMate
Gist Applications Inc.
GOJI
Hackworks
HBCI
Him & Her Incorporated
Hubdoc
invoicesherpa
ITS Global
Knockri
Launchcode
Luxsonic Technologies Inc.
Magest
Mikata Health
Moneris
NexTech AR Solutions
North Forge Technology Exchange
OPI Systems
Plusgrade
Podyssey Podcasts
QReserve
Save-On-Dev
SeamlessMD
Self-employment
Simcoe Harvest
SoulRooms Inc.
Tasttlig Corporation
Tasttling
Technologies Humanware inc.
The Fitting Room
unlearn.
Untribe
Visual College of Art and Design
Xero
Zaletskyi