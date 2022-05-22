API Endpoints
=====

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
----------------

.. code-block:: console

   line_id (String) : Bus Line unique ID
   line_code (String) : Bus Line unique Code (displayed in bus & station monitors)
   line_name_gr (String): Bus Line name in Greek
   line_name_en (String): Bus Line name in English
   route_id_XXX_from_YYYY (String): Route unique ID for this Bus Line
   XXX = Day of the week (mon,tue,wed,thu,fri,sat,sun)
   YYY = If the route starts from the initial stαtion of the route (example direction: ΕΥΟΣΜΟΣ -> ΑΡΙΣΤΟΤΕΛΟΥΣ) we use start
   YYY = If the route starts from the terminal stαtion of the route (example direction: ΑΡΙΣΤΟΤΕΛΟΥΣ -> ΕΥΟΣΜΟΣ) we use end





