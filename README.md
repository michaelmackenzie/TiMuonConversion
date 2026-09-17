# Muon conversion on titanium at Mu2e

This repo is intended to study muon conversion on titanium at Mu2e.

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
muse setup
time muse build --mu2eCompactPrint --mu2ePyWrap --mu2eCBD -j20
```
