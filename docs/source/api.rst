API Endpoints
=====


.. _/:

GET /
------------

Returns some project information and internal JSON formated endpoint documentation

.. code-block:: console

   https://oasth-telematics-api.georgetomzaridis.eu/
   
API Response



.. code-block:: json

   [
      {
    "name": "OASTH Telematics API",
    "version": "0.0.1-beta",
    "author": "George Tomzaridis",
    "email": "georgetomzaridis@gmail.com",
    "github": "https://github.com/georgetomzaridis",
    "tech_stack": "Node.JS + Express.JS + Axios",
    "createdAt": "22/05/2022",
    "updatedAt": "22/05/2022 15:00:00",
    "desc": "Rest API for gathering OASTH Bus Telematics Data (real-time)",
    "endpoints": [
        {
            "method": "GET",
            "url": "/getBusLines",
            "desc": "Return all the bus lines"
        },
        {
            "method": "GET",
            "url": "/getRoutes",
            "desc": "Return all the bus routes"
        },
        {
            "method": "GET",
            "url": "/getRouteStops",
            "desc": "Return all the stops for every route"
        },
        {
            "method": "GET",
            "url": "/getBusStops",
            "desc": "Return all the bus stops"
        }
    ]

.. _getBusLines:

GET /getBusLines
------------

Returns all the Bus Lines

.. code-block:: console

   https://oasth-telematics-api.georgetomzaridis.eu/getBusLines
   
API Response



.. code-block:: json

   [
      {
        "line_id": "89",
        "line_code": " 21",
        "line_name_gr": " ΕΥΟΣΜΟΣ - ΑΡΙΣΤΟΤΕΛΟΥΣ",
        "line_name_en": " EVOSMOS - ARISTOTELOUS",
        "route_id_mon_from_start": " 182",
        "route_id_mon_from_end": " 183",
        "route_id_tue_from_start": " 182",
        "route_id_tue_from_end": " 183",
        "route_id_wed_from_start": " 182",
        "route_id_wed_from_end": " 183",
        "route_id_thu_from_start": " 182",
        "route_id_thu_from_end": " 183",
        "route_id_fri_from_start": " 182",
        "route_id_fri_from_end": " 183",
        "route_id_sat_from_start": " 182",
        "route_id_sat_from_end": " 183",
        "route_id_sun_from_start": " 182",
        "route_id_sun_from_end": " 183"
    }
   ]

Data structure


.. code-block:: console

   line_id (String) : Bus Line unique ID
   line_code (String) : Bus Line unique Code (displayed in bus & station monitors)
   line_name_gr (String): Bus Line name in Greek
   line_name_en (String): Bus Line name in English
   route_id_XXX_from_YYYY (String): Route unique ID for this Bus Line
   XXX = Day of the week (mon,tue,wed,thu,fri,sat,sun)
   YYY = If the route starts from the initial stαtion of the route (example direction: ΕΥΟΣΜΟΣ -> ΑΡΙΣΤΟΤΕΛΟΥΣ) we use start
   YYY = If the route starts from the terminal stαtion of the route (example direction: ΑΡΙΣΤΟΤΕΛΟΥΣ -> ΕΥΟΣΜΟΣ) we use end
   
   
   
.. _getRoutes:

GET /getRoutes
------------

Returns all the Routes

.. code-block:: console

   https://oasth-telematics-api.georgetomzaridis.eu/getRoutes
   
API Response

.. code-block:: json

   [
      {
        "route_id": "182",
        "line_id": "89",
        "route_name_gr": " ΜΕΤΑΒΑΣΗ",
        "route_name_en": " ΜΕΤΑΒΑΣΗ",
        "route_type": "1",
        "route_distance": "7936.61"
    },
    {
        "route_id": "183",
        "line_id": "89",
        "route_name_gr": " ΕΠΙΣΤΡΟΦΗ",
        "route_name_en": " ΕΠΙΣΤΡΟΦΗ",
        "route_type": "2",
        "route_distance": "8611.73"
    },
   ]

Data structure


.. code-block:: console

   route_id (String) : Route unique ID
   line_id (String) : Bus Line unique ID
   route_name_gr (String): Route name in Greek
   route_name_en (String): Route name in English
   route_type (String): Route type ID
   route_distance (String): Route total distance (start-end) in meters
   
   
 
.. _getRouteStops:

GET /getRouteStops
------------

Returns all the stops for every route

.. code-block:: console

   https://oasth-telematics-api.georgetomzaridis.eu/getRouteStops
   
API Response

.. code-block:: json

   [
      {
        "routestop_id": "160079",
        "route_id": "182",
        "stop_id": "830",
        "routestop_order": "1"
    },
    {
        "routestop_id": "160080",
        "route_id": "182",
        "stop_id": "986",
        "routestop_order": "2"
    },
    {
        "routestop_id": "160081",
        "route_id": "182",
        "stop_id": "941",
        "routestop_order": "3"
    },
   ]

Data structure


.. code-block:: console

   routestop_id (String) : Route Stop unique ID
   route_id (String) : Route unique ID
   stop_id (String): Stop unique ID
   routestop_order (String): Stops order
   
   
.. _getBusStops:

GET /getBusStops
------------

Returns all the bus stops

.. code-block:: console

   https://oasth-telematics-api.georgetomzaridis.eu/getBusStops
   
API Response

.. code-block:: json

   [
      {
        "bus_stop_id": "-2",
        "bus_stop_code": " 15011",
        "bus_stop_name_gr": " ΚΟΙΜΗΤΗΡΙΑ ΠΥΛΑΙΑΣ",
        "bus_stop_name_en": " KIMITIRIA PILEAS",
        "bus_stop_street_gr": " ΚΕΝΝΕΝΤΥ ΤΖΩΝ ΛΕΩΦ.",
        "bus_stop_street_en": " ΚΕΝΝΕΝΤΥ ΤΖΩΝ ΛΕΩΦ.",
        "bus_stop_heading": " 287",
        "bus_stop_cord_lat": "22.9942",
        "bus_stop_cord_lng": "40.6002",
        "bus_stop_type": "0",
        "bus_stop_amea": "0",
        "bus_stop_googlemaps_url": "https://www.google.com/maps/place/40.6002,22.9942"
    },
    {
        "bus_stop_id": "32",
        "bus_stop_code": " 1348",
        "bus_stop_name_gr": " Τ.Σ. ΠΛΑΤΕΙΑ ΕΛΕΥΘΕΡΙΑΣ",
        "bus_stop_name_en": " T.S. PLATIA ELEFTHERIAS",
        "bus_stop_street_gr": " ΜΗΤΡΟΠΟΛΕΩΣ ",
        "bus_stop_street_en": " ΜΗΤΡΟΠΟΛΕΩΣ ",
        "bus_stop_heading": " 111",
        "bus_stop_cord_lat": "22.9385",
        "bus_stop_cord_lng": "40.6343",
        "bus_stop_type": "0",
        "bus_stop_amea": "0",
        "bus_stop_googlemaps_url": "https://www.google.com/maps/place/40.6343,22.9385"
    },
   ]

Data structure


.. code-block:: console

   bus_stop_id (String) : Bus Stop unique ID
   bus_stop_code (String) : Bus Stop unique code (usage on telephony telematics services)
   bus_stop_name_gr (String): Bus Stop name in Greek
   bus_stop_name_en (String): Bus Stop name in English
   bus_stop_street_gr (String): Bus Stop street name in Greek
   bus_stop_street_en (String): Bus Stop street name in English
   bus_stop_heading (String): Bus Stop GPS Heading
   bus_stop_cord_lat (String): Bus Stop GPS Cordinates Latitude
   bus_stop_cord_lng (String): Bus Stop GPS Cordinates Longitude
   bus_stop_type (String): Bus Stop Type
   bus_stop_amea (String): If the Bus Stop can accessed by people with disabilities or wheelchairs (0 - false / 1 - true)
   bus_stop_googlemaps_url (String): Google maps location pin url 
  





