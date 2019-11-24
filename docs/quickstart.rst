Advanced Key Manager Quickstart
===============================

.. note::
    Due to certain limitations, the project as of v1.0 is marked a Complete Project,
    but merely for the examples to as they deal with input bindings. Once migrated to your project, all parts of
    the asset are modular.

Getting started with the system should be a quick and painless process. After you have downloaded the asset, open the created project.
It is highly recommended to try out the demos, and open up the classes to see their setup.

Migrating to your project
=========================

When you're ready, you can begin the process of migrating the Advanced Input Display Manager to your project.
To do so, simply right click on the ``AdvancedKeyManager`` folder, and find the ``Migrate`` option.

.. image:: https://i.gyazo.com/3c2a53561e78872ab87f60345804fdc9.png

A new window will appear, showing you all of the files you will be migrating.

.. image:: https://gyazo.com/2da4cc42efbe4518ee61e344e2008363.png

Next, you'll need to find your project's ``Content`` folder to send the asset to.

.. image:: https://gyazo.com/483c2b87a4420b3247403c5f71a47d52.png

Once complete, the Advanced Key Manager asset will now be in your other UE4 project!

Getting started
===============

Having inputs display in your game is also a quick and easy process. First you need to add the ``BP_KeyManagerComponent`` to your
custom ``PlayerController`` blueprint.

.. image:: https://gyazo.com/1e234c6b3788b5043554136ea467cd5e.png

Next, add an ``AnyKey`` input event and call the following nodes on your newly added component from within your  ``PlayerController`` blueprint:

.. image:: https://gyazo.com/ebeaa1f2ff48bfbba34a049cf003f3b6.png

``This will send input received by the ``PlayerController`` directly to the AKM input system.``

Now that input is set up, you can display it many different ways. The easiest would be to duplicate the ``DebugWidget`` from the ``Examples`` folder.
This will allow you to show the current active ``Action Preset`` automatically.


Create and spawn your duplicate of this widget from the `BeginPlay`` node of your ``PlayerController`` blueprint.

.. image:: https://i.gyazo.com/4970fc9ba518882d476f82c95599048d.png

Adding an action preset
=======================

Action presets are an easy way to show a specific set of inputs depending on your situation.
For example, the player needs to know he can jump, fire and reload when on foot. However,
once you've gotten into vehicle, inputs for handbrake, accelerate, etc... are needed. That's where
Action presets come into play.

To create an action preset, go into the defaults of your added ``BP_KeyManagerComponent`` and find the ``ActionPresets`` variable.
Once you find it, click the ``+`` to add a new

.. image:: https://gyazo.com/1e21111a747ab61562ab71d98052cda8.png

Now, set a name for the preset, and add all of the inputs that you want to display to the the ``ActionContexts`` of that preset.

.. note::
    The actions you set here **must** be the exact names of the action bindings you set in your project input settings!

.. image:: https://gyazo.com/7191007cd1c3571fb2734d84f2431467.png

Now call ``SetActionPreset`` from anywhere.

.. image:: https://i.gyazo.com/d915802c4478140cbe8949b15d863f48.png

Now when you play, you should see your input bindings shown on the screen!

.. image:: https://gyazo.com/d0b49d8a75fd89b7da12c92eb634c64f.png

Now you can start adding presets and showing input in different ways! I highly recommend going back the full project and picking apart all of the
examples as they go deeper than what was shown here!
