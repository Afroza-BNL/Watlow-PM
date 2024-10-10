TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = watlowPMApp
# watlowPMApp.dbd will be created and installed
DBD += watlowPMApp.dbd

# watlowPMApp.dbd will be made up from these files:
watlowPMApp_DBD += base.dbd

# Include dbd files from all support applications:
watlowPMApp_DBD += asyn.dbd
watlowPMApp_DBD += drvAsynIPPort.dbd
watlowPMApp_DBD += modbusSupport.dbd
watlowPMApp_DBD += devIocStats.dbd


# Add all the support libraries needed by this IOC
watlowPMApp_LIBS += asyn modbus devIocStats

# watlowPMApp_registerRecordDeviceDriver.cpp derives from watlowPMApp.dbd
watlowPMApp_SRCS += watlowPMApp_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
watlowPMApp_SRCS_DEFAULT += watlowPMAppMain.cpp
watlowPMApp_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#watlowPMApp_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
watlowPMApp_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

