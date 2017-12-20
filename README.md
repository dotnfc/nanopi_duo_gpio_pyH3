# nanopi_duo_gpio_pyH3

Python control of NanoPi-Duo GPIO (Allwinner H3) based on pyA20 0.2.1
When using GPIO make sure that the desired gpio is not used by another periphery.


references: 
https://www.olimex.com/wiki/A20-OLinuXino-MICRO
https://pypi.python.org/pypi/pyA20

# install
	
	python setup.py install 


# GPIO mapping

	PG6	TX1, UART1 TX
	PG7	RX1, UART1 RX
	PA15 	SPI1-MOSI
	PA16 	SPI1-MISO
	PA14 	SPI1-CLK
	PA13 	SPI1-CS
	PA12 	I2C0-SDA
	PA11 	I2C0-SCL
	PA4  	DTX, UART0 TX debug
	PA5  	DRX, UART0 RX debug
	PG11 	GPIO G11
	PL11 	IRRX, IrDa RX

# LEDs mappimg

	POWER_LED,  SUNXI_GPL(10),  1   },
	STATUS_LED,  SUNXI_GPA(10),  2   },



# GPIO METHODS

    init()      -   Make initialization of the module. Always must be called first.
    getcfg()    -   Read current configuration of gpio.
    setcfg()    -   Write configuration to gpio.
    input()     -   Return current value of gpio.
    output()    -   Set output value.
    pullup()    -   Set pull-up/pull-down.


The available constants are:

    NAME        -   EQUALS TO
    ====            =========
    HIGH        ->      1
    LOW         ->      0
    INPUT       ->      0
    OUTPUT      ->      1
    PULLUP      ->      1
    PULLDOWN    ->      2


The gpio are named two ways:

    By port name: PH0, PG2, PE10, etc.
    These can be imported from port module:

    >>> from pyA20.gpio import port
    >>> dir(port)

    By connector name and pin number: gpio2p12, gpio3p8, lcdp18, uext1p3 and etc.
    These can be imported from connector module:

    >>> from pyA20.gpio import connector
    >>> dir(connector)

Generally these constants are just an offset in the memory from the base GPIO address, so they can
be assigned to a number type variable.

    >>> led = port.PH2
    >>> print led
    226



# I2C METHODS

    init()      -   Make initialization of the module
    open()      -   Begin communication with slave device
    read()      -   Read from slave device
    write()     -   Write data to slave device
    close()     -   End communication with slave device


# SPI METHODS

    open()      -   Open SPI bus with given configuration
    read()      -   Read data from slave device without write
    write()     -   Write data to slave device without read
    xfer()      -   Do write and after that read
    close()     -   Close SPI bus












