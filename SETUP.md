# Rubycoin Trezor Firmware Update

Install the trezor python library:

    	$ pip install trezor

Clone the Repository:

    	$ git clone git@github.com:Durendal/trezor-mcu

Navigate into the repo

    	$ cd trezor-mcu

Build the firmware:

    	$ sudo ./build.sh

Hold down both buttons on the trezor and plug it in, this will load it in bootloader mode which is required to flash it.

Flash your trezor:

    	$ trezorctl firmware_update -f build/trezor-master.bin

You will be informed that the firmware is unofficial, this is normal and expected.

Restore your seed:

    	$ trezorctl recovery_device

You can verify that rubycoin was successfully added by running:

    	$ trezorctl list_coins
    	['Bitcoin', 'Testnet', 'Bcash', 'Namecoin', 'Litecoin', 'Dogecoin', 'Dash', 'Zcash', 'Bitcoin Gold', 'DigiByte', 'Monacoin', 'Fujicoin', 'Vertcoin', 'Rubycoin']

and verifying rubycoin appears in the list.

Generating addresses:

    	$ trezorctl get_address -n "m/44'/16'/0'/0/0" -c Rubycoin
    	RTpLSunwr9aCmKKfECQbW4SHCJjV6NE5kx

If for any reason you encounter an issue and are unable to boot into your trezor load it in bootloader mode and run:

    	$ trezorctl firmware_update

This will pull the latest official pre-compiled binary from their website and install it on the trezor
