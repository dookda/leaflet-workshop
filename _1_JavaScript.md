// ----------Basic JavaScript----------
var number = 1;
var decimal = 16.8;
var lastname = "homhuan"

var object = {
    firstName: "sakda",
    lastName: "homhuan"
}

// console.log(number)
// console.log(decimal)
// console.log(lastname)
// console.log(object)

// การใช้ operator
var x = 5;
var y = 2;
var z = x + y;

// console.log(z)

// function
function showMessage() {
    var userName = "sakda"
    console.log(userName)
}

// showMessage()

// return function
function add() {
    return 1 + 2
}

var addData = add();
// console.log(addData);

// parameter function
function plusOne(a) {
    return a + 1;
}

var a = plusOne(5)
// console.log(a)


// arrow function
let b = (a) => { return a + 2 }
let c = b(5)
// console.log(c);


// if 
let d = 5 + 4

if (d < 7) {
    // console.log("d < 7");
} else if (d == 8) {
    // console.log("d == 8");
} else {
    // console.log("d > 8");
}

// while loop
var e = 0;
while (e <= 5) {
    // console.log(e);
    e++;
}

// for loop
for (var f = 0; f <= 5; f += 1) {
    // console.log(f);
}


// object
var user = new Object;
let k = {}

// console.log(typeof (user), typeof (k));
// properties
user = {
    firstName: "sakda",
    lastName: "homhuan",
}

// console.log(user.firstName);

// method
user["sayHi"] = function () {
    return "hello";
}

// console.log(user.sayHi());



// ----------Basic Leaflet----------

var map = L.map('map', {
    scrollWheelZoom: true,
    center: [14.802808, 98.950170],
    zoom: 5
});
// base layers
var osm = L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png?{foo}', {
    foo: 'bar',
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
})

var Esri_WorldStreetMap = L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Street_Map/MapServer/tile/{z}/{y}/{x}', {
    attribution: 'Tiles &copy; Esri &mdash; Source: Esri, DeLorme, NAVTEQ, USGS, Intermap, iPC, NRCAN, Esri Japan, METI, Esri China(Hong Kong), Esri(Thailand), TomTom, 2012'
});

var google_road = L.tileLayer("https://{s}.google.com/vt/lyrs=r&x={x}&y={y}&z={z}", {
    maxZoom: 20,
    subdomains: ["mt0", "mt1", "mt2", "mt3"],
    lyr: "grod",
    isBase: 'yes'
});
var googleHybridge = L.tileLayer("https://{s}.google.com/vt/lyrs=y,m&x={x}&y={y}&z={z}", {
    maxZoom: 20,
    subdomains: ["mt0", "mt1", "mt2", "mt3"],
    lyr: "ghyb",
    isBase: 'yes'
});
var googleTerrain = L.tileLayer("http://{s}.google.com/vt/lyrs=t,m&x={x}&y={y}&z={z}", {
    maxZoom: 20,
    subdomains: ["mt0", "mt1", "mt2", "mt3"],
    lyr: 'gter',
    isBase: 'yes'
});
// wms layers
var thailand = L.tileLayer.wms("https://rti2dss.com/geoserver/th/wms?", {
    layers: 'th:province_4326',
    format: 'image/png',
    transparent: true,
    attribution: "map by rit2dss"
});


var baseLayers = {
    'แผนที่ osm': osm.addTo(map),
    Esri_WorldStreetMap: Esri_WorldStreetMap,
    google_road: google_road,
    googleHybridge: googleHybridge,
    googleTerrain: googleTerrain
};

var overlayLayers = {
    'ขอบเขตจังหวัด': thailand.addTo(map)
};

L.control.layers(baseLayers, overlayLayers).addTo(map)

// ----------Survey Leaflet----------
