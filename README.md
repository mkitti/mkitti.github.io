# mkitti.github.io

Personal Github website of Mark Kittisopikul.

I will post references and documentation for code that I am developing here.

## JavaCPP-HDF5 1.14 Javadoc

This is in progress at https://github.com/bytedeco/javacpp-presets/pull/1327

<a href="janelia/javacpp-hdf5/1.14.0-1.5.9-SNAPSHOT/javadoc/">JavaCPP-HDF5 Javadoc 1.14.0-1.5.9-SNAPSHOT</a>

To build the current SNAPSHOT do the following.

```
git clone --branch mkitti/hdf_hdfgroup https://github.com/mkitti/javacpp-presets.git
cd javacpp-presets
mvn install --projects .,hdf5
cd platform
mvn install --projects ../hdf5/platform
```

The future plan is to rebase the JHDF5 bindings on top of this.
https://unlimited.ethz.ch/display/JHDF/Documentation+Page

The four C files located at https://sissource.ethz.ch/sispub/jhdf5/-/tree/master/source/c will need to be ported to Java  and used via the org.bytedeco.hdf5 bindings.
* https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5VLStrHelperImp.c
* https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5fHelperImp.c
* https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5lHelperImp.c
* https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5pHelperImp.c

Of particular interest, we to build the capability to retrieve all chunk locations from <a href="janelia/javacpp-hdf5/1.14.0-1.5.9-SNAPSHOT/javadoc/org/bytedeco/hdf5/global/hdf5.html#H5Dchunk_iter(long,long,org.bytedeco.hdf5.H5D_chunk_iter_op_t,org.bytedeco.javacpp.Pointer)">H5Dchunk_iter</a>.
