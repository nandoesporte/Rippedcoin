Ripped development tree

Ripped is a PoS-based cryptocurrency.

Development process
----------------

For more information, as well as an immediately useable, binary version of
the Ripped client sofware, see http://www.Ripped.com.

License
-------
<strong>You can install using docker:</strong>
<code> docker --name ripped --net host -it cosmo9able/ripped </code>
After installing, you simply enter the ripped container and make the necessary adjustments in the /root/.ripped/ripped.conf file


Ripped is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

<strong>Begin build for ubuntu</strong> 

Dependencies:
 
<code>apt-get install build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev git libssl1.0.0-dbg libdb-dev libdb++-dev libboost-all-dev libminiupnpc-dev libminiupnpc-dev libevent-dev libcrypto++-dev libgmp3-dev libqtgui4 -y</code>


Build daemon

<code>cd src/</code>

<code>make -f makefile.unix</code>

Done, it should generate the Rippedd file inside the <code>src/</code> folder


<code>qmake && make</code>

Once you have done this, you can use your wallet, just use the following command:

<code>./Ripped-qt</code>



Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Ripped
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion with the devs and community.

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/nandoesporte/Rippedcoin/tags) are created
regularly to indicate new official, stable release versions of Ripped.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./Ripped-qt_test

