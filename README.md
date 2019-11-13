# PyOpenFec
A Python wrapper for the OpenFEC API. Documentation for this API can be found [here](https://api.open.fec.gov/developers)

## Don't use this version!

[Robert Townley's version](https://github.com/RobertTownley/pyopenfec) is the most recently updated (as of 12 Nov 2019) version of this library. It is the code you would get if you did `pip install pyopenfec` and it's what I would use if I were still doing campaign finance stuff.

## Installation

 1. Clone this repository
```
git clone https://github.com/jeremyjbowers/pyopenfec.git
```
   
 2. navigate into the new directory
```
cd pyopenfec
```

 3. (optional) start the virtual environment you'd like to install to

 4. run
```
python setup.py install
```

_Dependencies include [six](https://pypi.python.org/pypi/six) and [requests](https://pypi.python.org/pypi/requests) (will be installed by `setup.py`)_

## Examples

### Candidates

#### Candidate
The `Candidate` class holds fields for each candidate in the OpenFEC API.

A number of class and instance methods are available.

##### count
The `Candidate.count()` method will return the number of Candidate objects available for a given query. Note: This method returns an integer representing the number of items available in the OpenFEC API. It does not return a list of objects.
```
from pyopenfec import Candidate
candidate_count = Candidate.count(cycle=2016, office="P", candidate_status="C")
```

#### fetch
The `Candidate.fetch()` method will return a list of Candidate objects available for a given query. This method will automatically page through the results and return all objects available in the OpenFEC API.
```
from pyopenfec import Candidate
candidate_count = Candidate.count(cycle=2016, office="P", candidate_status="C")
candidates = Candidate.fetch(cycle=2016, office="P", candidate_status="C")
for candidate in candidates:
    print("{name}, {party}".format(name=candidate.name, party=candidate.party))
```
### Committees
tktk

### Reports
tktk
