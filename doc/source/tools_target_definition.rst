=====================================
Command line target definition scheme
=====================================

In Microprobe, the concept ``target`` is used to define where the code being
generated will be run/executed/simulated. Microprobe follows a GCC-like target
definition scheme, where a target is defined by a tuple as following:
                        
  **<arch-name>-<uarch-name>-<env-name>**
                  
where:
                        
 - **<arch-name>**: is the name of the architecture.
 - **<uarch-name>**: is the name of the microarchitecture.
 - **<env-name>**: is the name of the environment.
 
Therefore, possible target definitions could be:

 - **z13-z13-z64_linuc_gcc** for z13 C/asm code.
 - **z14-z14-z64_linux_gcc** for z14 C/asm code.
 - **power_v206-power7-ppc64_linux_gcc** for POWER7 C/asm code.
 - **power_v207-power8-ppc64_linux_gcc** for POWER8 C/asm code.
 
.. note::

   It is up to the user to specify a valid target definition tuple. If an 
   invalid target definition tuple is specified, the results are unpredictable.
 
--------------------
Generic tool options
--------------------
 
In most of the tools provided, one can use ``--list-*`` options to get the list of
definitions available in the default search paths or the paths specified by the
different ``--*-paths`` options
                        
======================================================================================= =======================================================
Flag/Argument                                                                           Description
======================================================================================= =======================================================
``-P SEARCH_PATH [SEARCH_PATH ...]``, ``--default_paths SEARCH_PATH [SEARCH_PATH ...]`` Default search paths for Microprobe target definitions
``-A ARCHITECTURE_PATHS``, ``--architecture-paths ARCHITECTURE_PATHS``                  Search path for architecture definitions. Microprobe
                                                                                        will search in these paths for architecture
                                                                                        definitions.
``-M MICROARCHITECTURE_PATHS``, ``--microarchitecture-paths MICROARCHITECTURE_PATHS``   Search path for microarchitecture definitions.
                                                                                        Microprobe will search in these paths for
                                                                                        microarchitecture definitions.
``-E ENVIRONMENT_PATHS``, ``--environment-paths ENVIRONMENT_PATHS``                     Search path for environment definitions. Microprobe
                                                                                        will search in these paths for environment definitions.
``--list-architectures``                                                                Generate a list of architectures available in the
                                                                                        defined search paths and exit.
``--list-microarchitectures``                                                           Generate a list of microarchitectures available in the
                                                                                        defined search paths and exit.
``--list-environments``                                                                 Generate a list of environments available in the
                                                                                        defined search paths and exit.
======================================================================================= =======================================================

---------------
Example outputs
---------------

.. rubric:: Example 1:

Command::

   > mp_target --list-architectures

Output:

.. program-output:: ../../targets/generic/tools/mp_target.py -P ../../targets/ --list-architectures

.. rubric:: Example 2:

Command::

   > mp_target --list-microarchitectures

Output:

.. program-output:: ../../targets/generic/tools/mp_target.py -P ../../targets/ --list-microarchitectures

.. rubric:: Example 3:

Command::

   > mp_target --list-environments

Output:

.. program-output:: ../../targets/generic/tools/mp_target.py -P ../../targets/ --list-environments
