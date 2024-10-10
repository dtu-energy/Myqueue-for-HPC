# Myqueue-for-HPC
[MyQueue](https://myqueue.readthedocs.io/en/latest/) is a program for submitting single jobs or maintaining jobs in a package in a HPC cluster or local machine. It supports SLURM,PBS,LSF.
To use MyQueue you need a configuration file specific to your HPC or local machine. Create a folder named `.myqueue` in your home directory and add a configurational file called `config.py` which consist of all the partitions in your HPC/local machine.
You can then, either download/clone the `config.py` file into your `.myqueue` directory, or just copy the contents of the file into a new `config.py` file.
When you have added your configuration file you can download MyQueue by the command `$ pip install myqueue`. To initiate MyQueue in a specific folder you need to write `$ mq init` in the terminal. It will then copy your `.myqueue` folder with the configuration file. Example `config.py` for a set of different HPC are presented in this repository.

Now you can begin using MyQueue.

To submit jobs using MyQueue you need to write a command like `$ mq submit test.py -R 24:xeon24:2d`. This command will submit a python script called `test.py` in the `xeon24` partitions with 24 nodes for 2 days. To keep track of your jobs you can use the command `$ mq ls`, which list your jobs. You can delete jobs from the list by using `$ mq rm`. For more details about commands use `--help` after a command.
To learn more please see the [MyQueue documentation](https://myqueue.readthedocs.io/en/latest/).

Note: If you are experiencing issues with submitting a VASP or similar calculation, try instead of `xeon24:24:1h` adding `xeon24:24:1:1h`. This will start a single process instead of 24 processes.

