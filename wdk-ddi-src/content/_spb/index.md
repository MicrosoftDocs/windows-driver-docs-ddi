---
UID: TP:spb
ms.assetid: 3a7cfcc1-ab14-3368-8c74-824602179f41
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Simple Peripheral Bus (SPB)


Overview of the Simple Peripheral Bus (SPB) technology.

To develop Simple Peripheral Bus (SPB), you need these headers:

 * [spbcx.h](..\spbcx\index.md)
 * [spbfuncenum.h](..\spbfuncenum\index.md)

For the programming guide, see [Simple Peripheral Bus (SPB)](https://docs.microsoft.com/en-us/windows-hardware/drivers/spb).


This section contains reference information about Windows driver support for simple peripheral buses (SPBs). The SPB category includes synchronous serial buses such as I²C and SPI. The SpbCx I/O Control Codes subsection applies both to SPB controller drivers and to device drivers for SPB-connected peripherals. The remaining subsections apply only to SPB controller drivers, and describe the device driver interface (DDI) between the SPB framework extension (SpbCx) and the SPB controller driver. For more information, see the Simple Peripheral Bus (SPB) Driver Design Guide.
In this section


Topic
Description




SpbCx Structures and Enumerations



This section describes the structures and enumerations that are defined for the SPB framework extension (SpbCx) library. These structures and enumerations are used by the methods and callback functions that are defined by the SpbCx library.





EVT_SPB_CONTROLLER_OTHER



An SPB controller driver's EvtSpbControllerIoOther event callback function handles device I/O control requests that are not handled by other event callback functions or by the SPB framework extension (SpbCx).





EVT_SPB_CONTROLLER_READ



An SPB controller driver's EvtSpbControllerIoRead event callback function reads data from the specified target device into the buffers that are supplied with the read request.





EVT_SPB_CONTROLLER_SEQUENCE



An SPB controller driver's EvtSpbControllerIoSequence event callback function performs a sequence of data transfers between the specified target device and the buffers that are supplied with the sequence request.





EVT_SPB_CONTROLLER_WRITE



An SPB controller driver's EvtSpbControllerIoWrite event callback function writes data to the specified target device from the buffers that are supplied with the write request.





EVT_SPB_CONTROLLER_LOCK



An SPB controller driver's EvtSpbControllerLock event callback function locks the SPB controller for accesses of a single target device on the bus.





EVT_SPB_CONTROLLER_UNLOCK



An SPB controller driver's EvtSpbControllerUnlock event callback function unlocks the SPB controller, which was locked by a previous call to the EvtSpbControllerLock event callback function.





EVT_SPB_TARGET_CONNECT



An SPB controller driver's EvtSpbTargetConnect event callback function opens a connection to a target device on the bus.





EVT_SPB_TARGET_DISCONNECT



An SPB controller driver's EvtSpbTargetDisconnect event callback function closes a connection to a target device that was previously opened by a call to the driver's  EvtSpbTargetConnect event callback function.





SPB_CONNECTION_PARAMETERS_INIT



The SPB_CONNECTION_PARAMETERS_INIT function initializes an  SPB_CONNECTION_PARAMETERS structure.





SPB_CONTROLLER_CONFIG_INIT



The SPB_CONTROLLER_CONFIG_INIT function initializes an SPB_CONTROLLER_CONFIG structure.





SPB_REQUEST_PARAMETERS_INIT



The SPB_REQUEST_PARAMETERS_INIT function initializes an SPB_REQUEST_PARAMETERS structure.





SPB_TRANSFER_DESCRIPTOR_INIT



The SPB_TRANSFER_DESCRIPTOR_INIT function initializes an  SPB_TRANSFER_DESCRIPTOR structure.





SpbControllerSetIoOtherCallback method



The SpbControllerSetIoOtherCallback method registers an SPB controller driver's EvtSpbControllerIoOther callback function.





SpbControllerSetRequestAttributes method



The SpbControllerSetRequestAttributes method  sets object attributes that will be used for all SPBREQUEST objects  that the SPB framework extension (SpbCx) delivers to the SPB controller driver.





SpbControllerSetTargetAttributes method



The SpbControllerSetTargetAttributes method sets object attributes that will be used for all SPBTARGET objects that the SPB framework extension (SpbCx) delivers to the SPB controller driver.





SpbDeviceInitConfig method



The SpbDeviceInitConfig method attaches the SPB framework extension (SpbCx) to the I/O-request chain for a WDFDEVICE (FDO or PDO) object that is to be created.





SpbDeviceInitialize method



The SpbDeviceInitialize method completes the initialization of the SPB controller driver after this driver creates the associated device object.





SpbRequestCaptureIoOtherTransferList method



The SpbRequestCaptureIoOtherTransferList method retrieves the SPB_TRANSFER_LIST structure in the input buffer of the custom IOCTL request.





SpbRequestComplete method



The SpbRequestComplete method completes an I/O request and supplies a completion status.





SpbRequestGetController method



The SpbRequestGetController method returns the WDFDEVICE handle to the device object for the SPB controller that the specified I/O request was sent to.





SpbRequestGetParameters method



The SpbRequestGetParameters method retrieves a set of SPB-specific parameter values from an I/O request.





SpbRequestGetTarget method



The SpbRequestGetTarget method retrieves the SPBTARGET handle from the specified I/O request.





SpbRequestGetTransferParameters method



The SpbRequestGetTransferParameters method retrieves the transfer parameters for an individual transfer in an I/O transfer sequence.





SpbTargetGetConnectionParameters method



The SpbTargetGetConnectionParameters method retrieves the connection parameters for a target device on the bus.





SpbTargetGetFileObject method



The SpbTargetGetFileObject method accepts, as an input parameter, an SPBTARGET handle to an open target device, and returns a WDFFILEOBJECT handle to this target.





SPB driver reference in SDK header files



This section lists header files and reference used to support for simple peripheral buses (SPB). The header files in this section are included in the Windows Software Development Kit (SDK).



 


Send comments about this topic to Microsoft

