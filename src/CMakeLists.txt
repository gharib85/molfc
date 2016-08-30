#add_definitions(-DMAXMEM=200000000)

add_executable(molfc3
active.f90
agric.f90
dos_t.f90
errors.f90
fc_t.f90
hypfun.f90
input.f90
intc.f90
iofiles.f90
iogeom.f90
iomatrix.f90
iomodes.f90
isotopes.f90
job_t.f90
matfun.f90
messages.f90
mkl_dfti.f90
molfc.f90
output.f90
parameters.f90
proc.f90
proc_t.f90
sysop.f90
sys_t.f90
tmderivative.f90
transf_t.f90
util.f90
vecm.f90
vibut.f90
xmvar.f90

fc/axsw.f90
fc/ctransf.f90
fc/fc.f90
fc/fc_h.f90
fc/fcint.f90
fc/fcint_h.f90
fc/fcio.f90
fc/itransf.f90
fc/mtransf.f90
fc/nattransf.f90
fc/spectrum.f90
fc/kubo.f90
fc/reorg.f90
fc/fcpt.f90

dos/dos.f90
)

# For 64bit machines
target_link_libraries(molfc3 slatec fox_dom mkl_lapack95_lp64 mkl_intel_lp64 mkl_intel_thread mkl_core iomp5 pthread)
# for 32bit machines
#target_link_libraries(molfc3 slatec xml mkl_intel mkl_intel_thread mkl_core iomp5 pthread)
#target_link_libraries(molfc3 slatec xml mkl_intel mkl_sequential mkl_core pthread)

install(TARGETS molfc3 DESTINATION /Users/lello/Applications/bin)
