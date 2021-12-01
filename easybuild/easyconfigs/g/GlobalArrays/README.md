# GlobalArrays instructions

  * [GlobalArrays home page](https://hpc.pnl.gov/globalarrays/))

      * [User Manual](https://hpc.pnl.gov/globalarrays/papers/GA-UserManual-Main.pdf)
        is very outdated. Better to check instructions on the GitHub.

  * [GlobalArrasy on GitHub](https://github.com/GlobalArrays/ga)


## EasyBuild

  * [GlobalArrrays support in the EasyBuilders repository](https://github.com/easybuilders/easybuild-easyconfigs/tree/develop/easybuild/easyconfigs/g/GlobalArrays)

  * There is no support for GlobalArrays in the CSCS repository

  * [GlobalArrays in Spack](https://github.com/spack/spack/tree/develop/var/spack/repos/builtin/packages/globalarrays)


### Version 5.8 for CrayGnu

  * Started from the one for intel/2020a from the EasyBuilders repository.

  * Potential issues to look at:

      * Which BLAS and LAPACK options to use to ensure the right interfaces?
        GlobalArray will use 8-byte integers on LUMI.

          * Note that the `--enable-i8` actually corresponds to the default
            behaviour of the configure script without an option to specify the
            integer precision as by default it is the size of a pointer.

      * Which transport to use? The default EasyConfig file uses `--with-mpi-ts`.
        For a full list of options, see the [GA GitHub README](https://github.com/GlobalArrays/ga)

          * `--with-mpi3` may make more sense on modern MPI implementations? Though
            spack also still uses `--with-mpi-ts` as the default value.

      * ELPA is a possible extension.
