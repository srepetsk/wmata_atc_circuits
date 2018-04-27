# WMATA ATC Track Circuits

* WMATA utilizes an Automatic Train Control system to safely space trains on the railroad
* ATC breaks the railroad up into a series of blocks several hundred of feet in length
* This repository lists all (or near-all) ATC track circuits across the revenue WMATA Metrorail network

## Where is this data from?

The data was obtained by Stephen Repetski on behalf of Greater Greater Washington/Rail Transit Ops in a PARP request.

## Data Contents

The following partial dataset from WMATA includes four columns descriptive of the ATC track circuits which make up the railroad:
* TRKLEN - the length of each track circuit; **NOTE**: The dataset appears to have some minor errors, so TRKLEN does not always match up to the summation of FROM_MEASURE and TO_MEASURE
* Track Name - the name of the track that the circuit is on
* FROM_MEASURE - the starting point of the track circuit, in feet
* TO_MEASURE - the ending point of the track circuit, in feet

## What is Automatic Train Control?

WMATA has some good [documentation](https://www.wmata.com/business/procurement/solicitations/documents/RFI%2002202015%20DRAFT%20SOW%20SYSTEMS.pdf#page=7) online that goes into great detail about what ATC is.

Greater Greater Washington similarly has a [quick primer](https://ggwash.org/view/4412/how-track-circuits-detect-and-protect-trains) about how ATC track circuits work within Metrorail to keep trains separated.

## Why are there no circuit IDs?

Each circuit is typically identified by a concatenation of the Track Name and the initial From Measurement (divided by 100 and rounded off). For instance the circuit on J1 with FROM_MEASURE 86295 would have an ID of J1-863.

**however**

This is not the case wherever interlockings on the railroad exist. Due to the switches which cross from one track to another, there are extra circuits in those areas with a different naming convention.
Those interlocking circuit names are not included in the data provided by WMATA.

## Interlockings

I will not attempt to include all circuit IDs here, but you are welcome to if you'd like (fork and submit a PR, if you dare! ;)
A typical interlocking includes 4 switches - 1A, 1B, 3A, and 3B - and each numbered pair sits diagonal from its mate. Circuits in interlockings follow a naming convention like: 1BT and 3BT. However, as is the case, this doesn't hold for larger interlockings where there are pocket tracks, or other types of turnouts.
