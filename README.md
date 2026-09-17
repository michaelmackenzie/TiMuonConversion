# Muon conversion on titanium at Mu2e

This repo is intended to study muon conversion on titanium at Mu2e.

## To do

- Add a starting geometry file for the Ti target
- Check where the MuBeam stage stops in Run 1A, if past the Ti target switch to the Run 1B MuBeam
- Add a muon stop fcl that produces stops in the aluminum and titanium targets
- Add CE simulation fcl for the titanium muon stops
- Evaluate the stopping rate and reconstruction efficiency for the Ti target

Start with a baseline target thickness, then version control the datasets for different target geometries.

## Setting up

```bash
# make a new area
mu2einit
cd /exp/mu2e/app/users/${USER}/
mkdir mu2eti
cd mu2eti

# Add the needed repos
git clone https://github.com/michaelmackenzie/TiMuonConversion.git
git clone --branch dev --single-branch https://github.com/michaelmackenzie/Stntuple.git
git clone https://github.com/michaelmackenzie/Mu2eEvtAna.git
git clone https://github.com/Mu2e/Offline.git
git clone https://github.com/Mu2e/mu2e-trig-config.git
git clone https://github.com/Mu2e/Production.git
git clone https://github.com/Mu2e/EventNtuple.git
git clone https://github.com/Mu2e/ArtAnalysis.git
git clone https://github.com/Mu2e/MLTrain.git
git clone https://github.com/Mu2e/EventDisplay.git
git clone https://github.com/michaelmackenzie/grim.git
```

Compile on mu2ebuild02
```bash
ssh mu2ebuild02
mu2einit
cd /exp/mu2e/app/users/${USER}/mu2eti/
# make a build dir on the data disk
mkdir -p /exp/mu2e/data/users/${USER}/builds/mu2eti/
ln -s /exp/mu2e/data/users/${USER}/builds/mu2eti build
muse setup
time muse build --mu2eCompactPrint --mu2ePyWrap --mu2eCBD -j20
```
