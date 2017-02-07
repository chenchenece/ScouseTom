# ScouseTom EIT System
The __ScouseTom__ is versatile Electrical Impedance Tomography (EIT) system. It comprises a commercial current source [Keithley 6221](http://www.tek.com/keithley-low-level-sensitive-and-specialty-instruments/keithley-ultra-sensitive-current-sources-seri) and EEG amplifiers e.g. [biosemi](http://www.biosemi.com/) or the [actiCHamp](http://www.brainvision.com/actichamp.html0), alongside custom switching/control circuitry and software.

![ScouseTom System Overview](https://raw.githubusercontent.com/EIT-team/ScouseTom/master/doc/figures/Graphical_Abstract.png)

## Making a ScouseTom
If you are interested in making a ScouseTom EIT system, please create an __issue__ in the repo or email us, we would love to help you!

__Checklist__
- Keithley 6221 Current source
- EEG system with sufficient bandwidth. The [biosemi](http://www.biosemi.com/) and  [actiCHamp](http://www.brainvision.com/actichamp.html0) ahve been used so far, and likely the [gtec](http://www.gtec.at/) or the [Open-Ephys](http://www.open-ephys.org/) will too
- Matlab - needed for [processing](https://github.com/EIT-team/Load_data) anyway. Control the system using the Matlab code [here](./src/matlab/)
- [Arduino Due](https://www.arduino.cc/en/Main/arduinoBoardDue) For the controller
- [Arduino Switch Board](./src/schematics/Ard_Shield) This controls the current source and the timing of switching current injection pairs
- [SwitchNetwork](./src/schematics/ScouseTom_SwitchNetwork) At least one, each for 37 channels. This connects the current source to the EEG system and the electrodes

### Citing this work
Please cite the journal article found [here](http://dx.doi.org/10.3390/s17020280)

```
Avery, J., Dowrick, T., Faulkner, M., Goren, N. and Holder, D., 2017. A Versatile and Reproducible Multi-Frequency Electrical Impedance Tomography System. Sensors, 17(2), p.280.
```

### Processing the data
To process the data you collect with this system, use the code found in [this repo](https://github.com/EIT-team/Load_data)

### Creating EIT images
Requires a forward model, generated by the code [here](https://github.com/EIT-team/PEITS), and the reconstruction code [here](https://github.com/EIT-team/Reconstruction)

## Keithley settings
Set on the front panel under `comm`, change `BAUD` to `57.2k` and `Terminator` to `<CR+LF>` (or whatever the one on the far RIGHT is)
