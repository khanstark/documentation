Logging In
==========

.. include:: ../_robot_anon.rst

What to expect when you log in to a Plone site

When you visit a Plone web site anonymously, or are given the web address for site maintenance, you'll see a *log in* button in the top-right corner like this:

.. code:: robotframework
   :class: hidden

   *** Keywords ***

   Highlight link
       [Arguments]  ${locator}
       Update element style  ${locator}  padding  0.5em
       Highlight  ${locator}

   *** Test Cases ***

   Take login link screenshot
       Go to  ${PLONE_URL}
       Highlight link  css=#personaltools-login
       Capture and crop page screenshot
       ...    ${CURDIR}/../_robot/login-link.png
       ...    css=#content-header
       ...    css=#above-content-wrapper

.. figure:: ../_robot/login-link.png
   :alt: login link
   :align: center

.. note::

    Your site administrator may have *hidden* the login link, in which case you can go directly to a URL she or he has provided.

After clicking the *log in* link, you'll see an input panel where you can type in your user name and password:

.. code:: robotframework
   :class: hidden

   *** Test Cases ***

   Take login screenshot
       Go to  ${PLONE_URL}/login
       Capture and crop page screenshot
       ...    ${CURDIR}/../_robot/login-popup.png
       ...    css=#content-core


.. figure:: ../_robot/login-popup.png
   :alt: login link
   :align: center


After logging in to a Plone web site you will see some indication of your name, as the last item on the :term:`toolbar`.
You can click on your name to perform some actions related to your user, covered in the following sections.

You (or the site administrator) can allow users to use their email address as login name.
This feature can be switched on in the Security settings control panel.
The effect is that on the registration form no field is shown for the user name.
On the login form the user is now asked to fill in an email address.