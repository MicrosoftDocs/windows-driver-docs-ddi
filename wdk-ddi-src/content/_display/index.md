---
UID: TP:display
ms.assetid: 4b099f8f-1e3b-398c-9d48-80f65f6c3468
ms.author: windowsdriverdev
ms.date: 04/20/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Display



Overview of the Display technology.

To develop Display, you need these headers:

 * [d3d10tokenizedprogramformat.hpp](..\d3d10tokenizedprogramformat\index.md)
 * [d3d10umddi.h](..\d3d10umddi\index.md)
 * [d3d11tokenizedprogramformat.hpp](..\d3d11tokenizedprogramformat\index.md)
 * [d3d12tokenizedprogramformat.hpp](..\d3d12tokenizedprogramformat\index.md)
 * [d3d12umddi.h](..\d3d12umddi\index.md)
 * [d3d9types.h](..\d3d9types\index.md)
 * [d3dcaps.h](..\d3dcaps\index.md)
 * [d3dhal.h](..\d3dhal\index.md)
 * [d3dkmddi.h](..\d3dkmddi\index.md)
 * [d3dkmdt.h](..\d3dkmdt\index.md)
 * [d3dkmthk.h](..\d3dkmthk\index.md)
 * [d3dukmdt.h](..\d3dukmdt\index.md)
 * [d3dumddi.h](..\d3dumddi\index.md)
 * [dispmprt.h](..\dispmprt\index.md)
 * [dxapi.h](..\dxapi\index.md)
 * [dxgiddi.h](..\dxgiddi\index.md)
 * [dxgitype.h](..\dxgitype\index.md)
 * [dxva.h](..\dxva\index.md)
 * [hdcpumdddi.h](..\hdcpumdddi\index.md)
 * [iddcx.h](..\iddcx\index.md)
 * [iddcxfuncenum.h](..\iddcxfuncenum\index.md)
 * [igpupvdev.h](..\igpupvdev\index.md)
 * [miracompanionddi.h](..\miracompanionddi\index.md)
 * [netdispumdddi.h](..\netdispumdddi\index.md)
 * [ntagp.h](..\ntagp\index.md)
 * [ntddvdeo.h](..\ntddvdeo\index.md)
 * [ntgdi.h](..\ntgdi\index.md)
 * [umdprovider.h](..\umdprovider\index.md)
 * [video.h](..\video\index.md)
 * [videoagp.h](..\videoagp\index.md)

For the programming guide, see [Display](https://docs.microsoft.com/en-us/windows-hardware/drivers/display).

This section contains reference pages for the Windows Display Driver Model (WDDM).

## User-Mode Interfaces Implemented By the Direct3D Runtime

This section describes the user-mode Direct3D display driver interfaces that the operating system implements through the Direct3D runtime.

- Direct3D Functions Called by User-Mode Display DriversThese are functions that the Microsoft Direct3D runtime supplies to the user-mode display driver. The Direct3D 10 and Direct 3D 11 runtime caches the currently bound state objects for applications, therefore the runtime also caches currently bound state objects for user-mode display drivers with low overhead. For each call that the user-mode display driver makes to a state-refresh callback function, the Direct3D 10 runtime makes a corresponding call to a driver state function in the same execution thread before returning to the calling code in the driver. To improve performance, the state-refresh callback functions do not perform any parameter validation.


The state-refresh callback functions are useful when you are trying to develop a stateless driver or building up command buffer preamble data. The state-refresh callback functions also allow the user-mode display driver to benefit from high watermarks that the Direct3D 10 runtime maintains. High watermarks indicate the largest slot index, which could be non-NULL; therefore, high watermarks improve traversals across such slots.


- Connecting and Configuring Displays Functions Called By User Mode Display DriversFunctions that support connecting and configuring displays. In addition to using the CCD APIs to set up the desktop display, hardware vendors must modify their Windows 7 Windows Display Driver Model (WDDM) display miniport drivers to support CCD.

- Wireless display callback functions called by Miracast user-mode driversThe operating system implements wireless display (Miracast) user-mode functions. Only Miracast user-mode drivers can call these functions.

- Multiplane overlay functions called by user-mode display driversContains user-mode multiplane overlay functions that the operating system implements.


## Interfaces Implemented By the User-Mode Display Driver

This section describes the interfaces that the user-mode display driver implements and that can be called by the operating system.

- User-Mode Display Driver FunctionsThe user-mode display driver DLL exports the OpenAdapter function and supplies pointers to adapter-specific functions through members of the D3DDDI_ADAPTERFUNCS structure when the runtime calls OpenAdapter.



- User-Mode Display Driver Structures and EnumerationsThe Microsoft Direct3D runtime passes pointers to these structures in parameters of the user-mode display driver functions. The User-Mode Display Driver includes structures and enumerations for Microsoft Direct 3D version 10, 10.1, 11, 11.1, 11.2, and 12.0.

- Wireless display interfaces implemented by Miracast user-mode driversThis type of driver runs in a standalone DLL.

- Direct3D rendering performance functions implemented by the user-mode driverFunctions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver implements in order to support Microsoft Direct3D rendering performance improvements

- Adaptive refresh functions implemented by the user-mode driverFunctions a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver must implement in order to support a 48-Hz adaptive refresh rate.

- Tiled resource functions implemented by the user-mode driver
Functions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver must implement in order to support the use and manipulation of tiled resources.

- DirectX Video Acceleration 2.0 Structures and EnumerationsStructures and enumeration types that are used by the DirectX Video Acceleration (VA) 2.0 User-Mode Display Driver Functions.


## Kernel-Mode Interfaces Implemented By the DirectX Graphics Kernel Subsystem

This section describes the kernel-mode interfaces that the Windows operating system implements through the Microsoft DirectX graphics kernel subsystem.

- Dxgkrnl Interface
Reference pages for functions that are implemented by the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys), and called by the display miniport driver.


- Video Present Network (VidPN) Manager InterfacesInterfaces that contain pointers to functions that are implemented by the video present network (VidPN) manager. Display miniport drivers can call these functions only in kernel mode.


- AGP InterfaceThese functions are implemented by the operating system and called by the display miniport driver

- Debug Report InterfaceThese functions are implemented by the operating system and called by the display miniport driver.

- Timed Operation InterfaceThese functions are implemented by the display port driver and called by the display miniport driver

- Simple Peripheral Bus (SPB) InterfaceA Windows Display Driver Model (WDDM) 1.2 and later display miniport driver can access bus resources on a system-on-a-chip (SoC) system by calling the Simple Peripheral Bus (SPB) functions.

- System Firmware Table InterfaceThe System Firmware Table interface contains functions that user-mode display drivers can use to read and enumerate the system firmware table. These functions are supplied by the Microsoft DirectX graphics kernel subsystem and can be called by WDDM 1.2 and later user-mode display drivers.

- Wireless display (Miracast) display callback interfaceThe Miracast display callback interface contains functions that are implemented by the Microsoft DirectX graphics kernel subsystem to support wireless (Miracast) displays. This interface is supported starting in Windows 8.1.

- Direct3D Shader CodesA command to create a pixel or vertex shader is composed of a group of shader codes. These codes instruct the driver on how to create the shader.


## Kernel-Mode Interfaces Implemented By the Display Miniport Driver

The display miniport driver exports only one function: DriverEntry. All other functions implemented by the display miniport driver are called through function pointers supplied by the display miniport driver at run time. The display miniport driver can supply function pointers to the display port driver and to other operating system components in more than one way.

- Functions Registered by DriverEntry of Display Miniport DriverFunctions that the display miniport driver implements, and are registered by the DriverEntry function of the display miniport driver. Some of those functions must be implemented by every display miniport driver. Other functions are either optional or required only for drivers of display adapters that have particular features.


- Brightness Control Interface
Integrated display panel brightness control interface functions are implemented by some display miniport drivers.

- Brightness Control Interface V. 2 (Adaptive and Smooth Brightness Control)
The Brightness Control Interface Version 2 lets a display miniport driver reduce power to the display backlight and still smoothly adapt to changes in ambient light and user requests to change brightness. Starting with Windows 8, if the system includes an ambient light sensor, the driver must support the Brightness Control Interface V. 2.



- OPM InterfaceThe Output Protection Manager (OPM) interface functions are implemented by some display miniport drivers.

- I2C InterfaceThe inter-integrated circuit (I2C) interface functions, which are implemented by some display miniport drivers

- Kernel Mode Display-Only Driver (KMDOD) InterfaceThe DriverEntry function of the kernel mode display-only driver (KMDOD) supplies function pointers to the display port driver by filling in all members of a KMDDOD_INITIALIZATION_DATA structure and then passing that structure to the DxgkInitializeDisplayOnlyDriver function. DxgkDdiPresentDisplayOnly is the only function with a function pointer in KMDDOD_INITIALIZATION_DATA that is unique to a KMDOD.Note that if a KMDOD does not support the VSync control feature, it should not implement certain functions.
Note  A KMDOD does not support the sleep power state. If it is placed in the sleep state, the driver will cause a system bugcheck to occur. There is no workaround available, by design.
If the current display driver is not a Windows Display Driver Model (WDDM) 1.2 compliant driver, a KMDOD might fail to install, with error code 43 displayed. The KMDOD driver is actually installed, but it cannot be started. The workaround for this issue is to switch to the Microsoft Basic Display Adapter Driver before installing the KMDOD, or simply to reboot your system after installing the KMDOD.

 


- Wireless display (Miracast) interfaceContains kernel-mode functions that are implemented by display miniport drivers that support wireless (Miracast) displays. This interface is supported starting in Windows 8.1.


- Multiplane overlay kernel-mode driver-implemented functionsContains functions that are implemented by display miniport drivers and support multiplane overlays.

- Display Miniport Driver Structures, Enumerations, and I/O Control Codes

## OpenGL Functions Called by OpenGL Installable Client Drivers

Describe the functions, the structures and the enumeration types that the OpenGL installable client driver (ICD) uses to access Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) services. To call the OpenGL functions, the OpenGL ICD must load Gdi32.dll and initialize use of the functions.

## IddCx Driver Class Extension Reference

 In the Windows IddCx drivers architecture, the class extension is the Microsoft-provided driver (): display class extension (IddCx). This is an in-box driver included in the SDK.

The client driver is written by an IHV/OEM. That driver is referred to as the display client driver.

The driver support methods are implemented by the IddCx library. These functions are implemented by your client driver for the display device. IddCx invokes these functions to notify the client driver about events.


## User-mode driver allocation logging

These functions, enumeration, and structure are from the Umdprovider.h and Umdetw.h headers, to log events in your user-mode display driver.

## Reference Topics for Windows 8.1

Device driver interfaces (DDIs) that are new or updated for Windows 8.1 support new features for version 1.3 of the WDDM. For links to all new DDIs, and to in-depth discussion of how to use the new features, see What's new for Windows 8.1  display drivers (WDDM 1.3).

Kernel-mode driver interfaces are declared in these headers:

- D3d9types.h
- D3dkmddi.h
- D3dkmdt.h
- Dispmprt.h
- Dxgiddi.h

User-mode driver interfaces are declared in these headers:

- D3d10umddi.h
- D3dkmthk.h (OpenGL functions)
- D3dukmdt.h (includes kernel-mode definitions)
- D3dumddi.h
- Netdispumdddi.h (new for Windows 8.1)

ETW events for user-mode drivers are declared in the Umdprovider.h header.

## Reference Topics for Windows 8


DDIs that are new or updated for Windows 8 support new features for version 1.2 of the WDDM. For links to all new DDIs, and to in-depth discussion of how to use the new features, see What's new for Windows 8 display drivers.

Kernel-mode driver interfaces are declared in these headers:

- D3d9types.h
- D3dkmddi.h
- D3dkmdt.h
- Dispmprt.h
- Dxgiddi.h

User-mode driver interfaces are declared in these headers:

- D3d10umddi.h
- D3dkmthk.h (OpenGL functions)
- D3dukmdt.h (includes kernel-mode definitions)
- D3dumddi.h

ETW events for user-mode drivers are declared in the Umdprovider.h header.

## Windows 2000 Display Driver Model (XDDM) Reference

The Windows 2000 Display Driver Model (XDDM) Reference apply to printer drivers and to drivers in the Microsoft Windows 2000 display driver model (XDDM), but not to drivers in the Windows Vista display driver model (WDDM).


You can write display adapter drivers according to the Windows Vista display driver model or according to the Windows 2000 display driver model. Windows Vista supports both display driver models. Operating systems prior to Windows Vista support only the Windows 2000 display driver model.Note  XDDM and VGA drivers will not compile on Windows 8 and later versions. If display hardware is attached to a Windows 8 computer without a driver that is certified to support Windows Display Driver Model (WDDM) 1.2 or later, the system defaults to running the Microsoft Basic Display Driver.
 


The Windows 2000 Display Driver Model (XDDM) include the following driver interfaces:

- DirectDraw Display Driver Interfaces
- Direct3D Display Driver Interfaces

- DirectX Video Acceleration Interfaces
- Video Miniport Driver Functions and Structures
- Video Port Driver Functions
- GDI Functions

Send comments about this topic to Microsoft

