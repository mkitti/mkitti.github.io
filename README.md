# mkitti.github.io

Personal Github website of Mark Kittisopikul.

I will post references and documentation for code that I am developing here.

## JavaCPP-HDF5 1.14.0-1.5.9-SNAPSHOT Javadoc

This is in progress at <a href="https://github.com/bytedeco/javacpp-presets/pull/1327">https://github.com/bytedeco/javacpp-presets/pull/1327</a>.

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
<a href="https://unlimited.ethz.ch/display/JHDF/Documentation+Page">https://unlimited.ethz.ch/display/JHDF/Documentation+Page</a>

The four C files located in the <a href="https://sissource.ethz.ch/sispub/jhdf5/-/tree/master/source/c">source tree</a> will need to be ported to Java and used via the `org.bytedeco.hdf5` bindings.
* <a href="https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5VLStrHelperImp.c">h5VLStrHelperImp.c</a>
* <a href="https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5fHelperImp.c">h5fHelperImp.c</a>
* <a href="https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5lHelperImp.c">h5lHelperImp.c</a>
* <a href="https://sissource.ethz.ch/sispub/jhdf5/-/blob/master/source/c/h5pHelperImp.c">h5pHelperImp.c</a>

Of particular interest, we to build the capability to retrieve all chunk locations from <a href="janelia/javacpp-hdf5/1.14.0-1.5.9-SNAPSHOT/javadoc/org/bytedeco/hdf5/global/hdf5.html#H5Dchunk_iter(long,long,org.bytedeco.hdf5.H5D_chunk_iter_op_t,org.bytedeco.javacpp.Pointer)">H5Dchunk_iter</a>.
