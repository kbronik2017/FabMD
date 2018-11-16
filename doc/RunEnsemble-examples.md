## Run Ensemble Examples

### lammps_ensemble_example1

These examples assume that you have been able to run the basic FabSim examples described in ``FabMD-examples.md``, and that you have installed and configured LAMMPS on the target machine.

To run type:
``fab localhost lammps_ensemble:lammps_ensemble_example1,input_name_in_config=data.peptide``

FabMD looks for a directory called `lammps_ensemble_example1` in `config_files`. It then looks for a sweep directory (by default called `SWEEP`) that contains a number of input files to iterate through. All the files in `lammps_ensemble_example1` directory and one of the sweep directory files will be copied to the host in separate directories (one for each sweep file) and executed in the normal way. 
`lammps_ensemble` requires `input_name_in_config` to be set on the command line, this is the name that each of the sweep files will be changed to when copied to the host. 
This example essentially runs the same input script with different topology (data) files.

## lammps_ensemble_example2

This example runs 3 simulations with different input files, which vary the simulation temperature, using the same topology file.

To run type:
``fab localhost lammps_ensemble:lammps_ensemble_example2,input_name_in_config=in.lammps``

NOTE if your input filename is not the same as the one set in ``FabMD/default_settings/lammps.yaml``, then you will have to specify this in the command line. For example the following command may be more suitable but will run the exact same simulations:
``fab localhost lammps_ensemble:lammps_ensemble_example2,input_name_in_config=in.peptide,lammps_input=in.peptide``
