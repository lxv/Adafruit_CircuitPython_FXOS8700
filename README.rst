==================================================================================
CircuitPython driver for the Adafruit FSOX8700 Accelerometer/Magnetometer Breakout
==================================================================================

.. image:: https://readthedocs.org/projects/circuitpython-FXOS8700/badge/?version=latest
    :target: https://circuitpython.readthedocs.io/projects/FXOS8700/en/latest/
    :alt: Documentation Status

.. image :: https://img.shields.io/discord/327254708534116352.svg
    :target: https://discord.gg/nBQh6qu
    :alt: Discord

Introduction
------------

CircuitPython module for the FSOX8700 Accelerometer/Magnetometer.
Technical documentation on FSOX8700 chip is available online from
`NXP <https://www.nxp.com/files-static/sensors/doc/data_sheet/FXOS8700CQ.pdf>`_.
The chip is available on a nice breakout `board from Adafruit <https://www.adafruit.com/product/3463>`_,
see the guide at `NXP Precision 9DoF Breakout <https://learn.adafruit.com/nxp-precision-9dof-breakout>`_.

Dependencies
------------
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_
* `Bus Device <https://github.com/adafruit/Adafruit_CircuitPython_BusDevice>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Usage Example
-------------

Getting the readings from accelerometer/magnetometer is easy! First, import ``board`` module for pin definitions
for your specific microcontroller board, ``busio`` for native I2C communication and the driver library
itself.

.. code-block:: python

  import board
  import busio
  import fxos8700

Next, initialize the I2C bus in a ``with`` statement so it always gets shut down ok.
Then, instantiate FSOX8700 class:

.. code-block:: python

  # Read current acceleration for all three axes and print it out
  with busio.I2C(board.SCL, board.SDA) as i2c:
      s = fxos8700.FXOS8700(i2c)
      print(s.acceleration)

Contributing
------------

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/lxv/CircuitPython_FXOS8700/blob/master/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.

API Reference
-------------

.. toctree::
   :maxdepth: 2

   api
