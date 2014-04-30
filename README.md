contents
========
todo

introduction
============

Varys is a python package for anyone who has to work with behavioral data
logs.

Chances are, you need that data in another format before you can work with it.

Chances are, you have some collection of scripts around somewhere that can
parse format A, other scripts that write format B, and somewhere in the middle
you'll sandwich some logic that actually has something to do with your
experiment.

Our goal is to reduce the load down to this last bit.

Varys breaks its work into three segments: LogParser, EventBuilder, and
FileWriter. Of these, only EventBuilder needs to be customized per experiment.

LogParser is meant to grow with time to be able to parse an increasingly
diverse list of input sources. At the moment we support simple TDF and CSV
formats, as well as the FIDL format used by the eponymous software package
from Washington University. But we're willing and anxious to work with users
to expand that list.

EventBuilder takes input from a LogParser, and turns it into a list of
"event" dictionaries. These can contain arbitrary values, but at a minumum
must contain "name," "onset" and "duration."

FileWriter takes these ordered dictionaries, and writes files consumable by
analysis packages. At the time of this writing, we support SPM, FIDL, TDF, and
python's Pickle, but again we're willing and eagre to expand this list.

We've thrown in some special options for working with neuroimaging data, for
concatenating runs, and other fun stuff too.

So please, take a look at the examples list, see if any of them sound like
your situation, and feel free to use them as a starting point for your own
work.

installation
============

pip
---

First, install the requirements listed in requirements.txt. You'll need scipy
to write matlab files, and we use chardet to determine the text encoding of
log files.

sudo pip install -r requirements.txt



