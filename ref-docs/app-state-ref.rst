.. _app_state:

========================
AppState
========================

The ``AppState`` object encapsulates information about the state of a SmartApp attribute.
These attributes are usually set in SmartApps using the sendEvent method.
Here is a small code snippet that illustrates a potential use case.

.. code-block:: groovy

    // If the current state of the "status" attribute is not what is expected,
    // then send and event to update it.
    if (app.currentState("status")?.value != "expectedValue") {
        def text = "$app.label someAction"
        sendEvent(name: "status", value: "expectedValue", linkText: app.label,
            descriptionText: text, eventType:"SOLUTION_EVENT", data: [icon: icon, backgroundColor: color])
    }

----

dateValue
---------

The value of this Event, if the value can be parsed to a Date.

**Signature:**
    ``Date dateValue``

**Returns:**
    `Date`_ - the value of this Event as a Date.

.. warning::

    ``dateValue`` will throw an Exception if the value of the event is not parseable to a Date.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHander(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as an Double
        // throws an exception of the value is not convertable to a Date
        try {
            log.debug "The dateValue of this event is ${myState.dateValue}"
            log.debug "myState.dateValue instanceof Date? ${myState.dateValue instanceof Date}"
        } catch (e) {
            log.debug "Trying to get the dateValue for ${myState.name} threw an exception: $e"
        }
    }

----

id
--

The unique system identifier for this event.

**Signature:**
    ``String id``

**Returns:**
    `String`_ - the unique device identifier for this event.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        log.debug "event id: ${myState.id}"
    }

----

descriptionText
---------------

The description of the event that is to be displayed to the user in the mobile application.

**Signature:**
    ``String descriptionText``

**Returns:**
    `String`_ - the description of this event to be displayed to the user in the mobile application.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        log.debug "event description text: ${myState.descriptionText}"
    }

----

doubleValue
-----------

The value of this Event, if the value can be parsed to a Double.

**Signature:**
    ``Double doubleValue``

**Returns:**
    `Double`_ - the value of this Event as a Double.

.. warning::

    ``doubleValue`` will throw an Exception if the value of the event is not parseable to a Double.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHander(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as a Double
        // throws an exception of the value is not convertible to a Double
        try {
            log.debug "The doubleValue of this event is ${myState.doubleValue}"
            log.debug "myState.doubleValue instanceof Double? ${myState.doubleValue instanceof Double}"
        } catch (e) {
            log.debug "Trying to get the doubleValue for ${myState.name} threw an exception: $e"
        }
    }

----

floatValue
----------

The value of this Event as a Float, if it can be parsed into a Float.

**Signature:**
    ``Float foatValue``

**Returns:**
    `Float`_ - the value of this Event as a Float.

.. warning::

    ``floatValue`` will throw an Exception if the Event's value is not parseable to a Float.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as an Float
        // throws an exception if not convertable to Float
        try {
            log.debug "The floatValue of this event is ${myState.floatValue}"
            log.debug "myState.floatValue instanceof Float? ${myState.floatValue instanceof Float}"
        } catch (e) {
            log.debug "Trying to get the floatValue for ${myState.name} threw an exception: $e"
        }
    }

----

integerValue
------------

The value of this Event as an Integer.

**Signature:**
    ``Integer integerValue``

**Returns:**
    `Integer`_ - the value of this Event as an Integer.

.. warning::

    ``integerValue`` throws an Exception of the Event value cannot be parsed to an Integer.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as an Integer
        // throws an exception if not convertable to Integer
        try {
            log.debug "The integerValue of this event is ${myState.integerValue}"
            log.debug "The integerValue of this event is an Integer: ${myState.integerValue instanceof Integer}"
        } catch (e) {
            log.debug "Trying to get the integerValue for ${myState.name} threw an exception: $e"
        }
    }

----

isoDate
-------

Acquisition time of this Event as an ISO-8601 String.

**Signature:**
    ``String isoDate``

**Returns:**
    `String`_ - The acquisition time of this Event as an ISO-8601 String.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        log.debug "event isoDate: ${myState.isoDate}"
    }

----

jsonValue
---------

Value of the Event as a parsed JSON data structure.

**Signature:**
    ``Object jsonValue``

**Returns:**
    `Object`_ - The value of the Event as a JSON structure

.. warning::

    ``jsonValue`` throws an Exception if the value of the Event cannot be parsed into a JSON object.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as a JSON structure
        // throws an exception if the value is not convertable to JSON
        try {
            log.debug "The jsonValue of this event is ${myState.jsonValue}"
        } catch (e) {
            log.debug "Trying to get the jsonValue for ${myState.name} threw an exception: $e"
        }
    }

----

lastUpdated
-----------

The last time this event was updated as a Date.

**Signature:**
    ``Date lastUpdated``

**Returns:**
    `Date`_ - The last time this event was updated as a Date.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        log.debug "event was last updated: ${myState.lastUpdated}"
    }

----

longValue
---------

The value of this Event as a Long.

**Signature:**
    ``Long longValue``

**Returns:**
    `Long`_ - the value of this Event as a Long.

.. warning::

    ``longValue`` throws an Exception if the value of the Event cannot be parsed to a Long.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as an Long
        // throws an exception if not convertable to Long
        try {
            def evtLongValue = myState.longVaue
            log.debug "The longValue of this event is $evtLongValue"
            log.debug "evt.longValue instanceof Long? ${evtLongValue instanceof Long}"
        } catch (e) {
            log.debug "Trying to get the longValue for ${myState.name} threw an exception: $e"
        }
    }

----

name
----

The name of this Event.

**Signature:**
    ``String name``

**Returns:**
    `String`_ - the name of this event.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        log.debug "the name of this event: ${myState.name}"
    }

----

numberValue
-----------

The value of this Event as a Number.

**Signature:**
    ``BigDecimal numberValue``

**Returns:**
    `BigDecimal`_ - the value of this event as a BigDecimal.

.. warning::

    ``numberValue`` throws an Exception if the value of the Event cannot be parsed to a BigDecimal.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as an Number
        // throws an exception if the value is not convertable to a Number
        try {
            def evtNumberValue = myState.numberValue
            log.debug "The numberValue of this event is ${evtNumberValue}"
            log.debug "evt.numberValue instanceof BigDecimal? ${evtNumberValue instanceof BigDecimal}"
        } catch (e) {
            log.debug "Trying to get the numberValue for ${myState.name} threw an exception: $e"
        }
    }

----

numericValue
------------

The value of this Event as a Number.

**Signature:**
    ``BigDecimal numericValue``

**Returns:**
    `BigDecimal`_ - the value of this event as a BigDecimal.

.. warning::

    ``numericValue`` throws an Exception if the value of the Event cannot be parsed to a BigDecimal.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as an Number
        // throws an exception if the value is not convertable to a BigDecimal
        try {
            def evtNumberValue = myState.numericValue
            log.debug "The numericValue of this event is ${evtNumberValue}"
            log.debug "evt.numericValue instanceof BigDecimal? ${evtNumberValue instanceof BigDecimal}"
        } catch (e) {
            log.debug "Trying to get the numericValue for ${myState.name} threw an exception: $e"
        }
    }

----

unit
----

The unit of measure for this Event, if applicable.

**Signature:**
    ``String unit``

**Returns:**
    `String`_ - the unit of measure of this Event, if applicable. ``null`` otherwise.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        log.debug "The unit for this event: ${myState.unit}"
    }

----

value
-----

The value of this Event as a String.

**Signature:**
    ``String stringValue``

**Returns:**
    `String`_ - the value of this event as a String.

**Example:**

.. code-block:: groovy

    def eventHandler(evt) {
        def myState = app.currentState("someAttribute")
        log.debug "The value of this event as a string: ${myState.value}"
    }

----

xyzValue
--------

Value of the event as a 3-entry Map with keys 'x', 'y', and 'z' with BigDecimal values. For example:

.. code-block:: groovy

    [x: 1001, y: -23, z: -1021]

Typically only useful for getting position data from the "Three Axis" Capability.

**Signature:**
    ``Map<String, BigDecimal> xyzValue``

**Returns:**
    `Map`_ < `String`_ , `BigDecimal`_ > - A map representing the X, Y, and Z coordinates.

.. warning::

    ``xyzValue`` throws an Exception if the value of the Event cannot be parsed to an X-Y-Z data structure.

    You should wrap calls in a try/catch block.

**Example:**

.. code-block:: groovy

    def positionChangeHandler(evt) {
        def myState = app.currentState("someAttribute")
        // get the value of this event as a 3 entry map with keys
        //'x', 'y', 'z', and BigDecimal values
        // throws an exception if the value is not convertable to a Date
        try {
            log.debug "The xyzValue of this event is ${myState.xyzValue }"
            log.debug "myState.xyzValue instanceof Map? ${myState.xyzValue  instanceof Map}"
        } catch (e) {
            log.debug "Trying to get the xyzValue for ${myState.name} threw an exception: $e"
        }
    }

.. _BigDecimal: http://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html
.. _Boolean: http://docs.oracle.com/javase/7/docs/api/java/lang/Boolean.html
.. _Date: http://docs.oracle.com/javase/7/docs/api/java/util/Date.html
.. _Double: https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html?is-external=true
.. _Float: https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html
.. _Integer: https://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html
.. _Object: http://docs.oracle.com/javase/7/docs/api/java/lang/Object.html
.. _String: http://docs.oracle.com/javase/7/docs/api/java/lang/String.html
.. _Map: http://docs.oracle.com/javase/7/docs/api/java/util/Map.html
.. _Number: http://docs.oracle.com/javase/7/docs/api/java/lang/Number.html
.. _Long: https://docs.oracle.com/javase/7/docs/api/java/lang/Long.html
