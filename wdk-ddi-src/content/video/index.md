---
UID: NA:video
ms.assetid: 674c88a6-47af-3f20-8f7a-e79f72def812
ms.author: windowsdriverdev
ms.date: 04/20/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Video.h header





This header is used by display. For more information, see:

- [Display](../_display/index.md)

This section provides reference pages for the functions that are implemented by the video miniport driver. The video miniport driver exports only one function: DriverEntry. All other functions implemented by the video miniport driver are called through function pointers supplied by the video miniport driver at run time. There are several mechanisms by which the video miniport driver supplies function pointers to the video port driver and to other operating system components.

When the I/O manager calls the video miniport driver's DriverEntry function, the video miniport driver provides the video port driver with pointers to a core set of functions. Those function pointers are among the members of a VIDEO_HW_INITIALIZATION_DATA structure that the video miniport driver passes to the VideoPortInitialize function.

If the video miniport driver calls the video port driver's VideoPortDDCMonitorHelper function, then the video miniport driver must implement a set of inter-integrated circuit (I2C) functions that read and write data bits to the serial clock and data lines of the I2C bus. The video miniport driver supplies the video port driver with pointers to those functions in one of the parameters that it passes to VideoPortDDCMonitorHelper.

If the video miniport driver is VGA-compatible (most are not), then it may implement a set of SVGA functions. To register the SVGA functions, the video miniport driver's HwVidFindAdapter function places function pointers in the Routine members of an array of EMULATOR_ACCESS_ENTRY structures.

Certain video miniport drivers implement a set of DxApi functions. The video miniport driver supplies the operating system with pointers to those functions when its HwVidQueryInterface function receives a request for the interface identified by GUID_DxApi.

In addition to the core, I2C, DxApi, and SVGA functions, the video miniport driver can implement a few other functions, each of which is registered individually. For example, the video miniport driver can implement the HwVidBugcheckCallback function, which it registers by calling VideoPortRegisterBugcheckCallback.

For more detailed information about how the various types of video miniport driver functions are registered, see the following topics:

Send comments about this topic to Microsoft

