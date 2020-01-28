---
UID: NC:video.PDRIVER_IO_PORT_USHORT
title: PDRIVER_IO_PORT_USHORT (video.h)
description: SvgaHwIoPortUshort traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of USHORT-sized data.
old-location: display\svgahwioportushort.htm
tech.root: display
ms.assetid: 304656b4-ebbe-4cb1-8735-2e03bec71f9f
ms.date: 05/10/2018
ms.keywords: PDRIVER_IO_PORT_USHORT, PDRIVER_IO_PORT_USHORT callback, SvgaHwIoPortUshort, SvgaHwIoPortUshort callback function [Display Devices], VideoMiniport_Functions_756e549c-fadc-49ae-b356-c94893809e01.xml, display.svgahwioportushort, video/SvgaHwIoPortUshort
f1_keywords:
 - "video/SvgaHwIoPortUshort"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- video.h
api_name:
- SvgaHwIoPortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# PDRIVER_IO_PORT_USHORT callback function


## -description


<i>SvgaHwIoPortUshort</i> traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of USHORT-sized data.


## -parameters




### -param Context

Specifies the miniport driver-determined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of VIDEO_PORT_CONFIG_INFO.


### -param Port

Specifies the mapped I/O port to be trapped.


### -param AccessMode

Specifies the type of access allowed, which can be one or a combination (ORed) of the following values:


<dl>
<dt>EMULATOR_READ_ACCESS</dt>
<dt>EMULATOR_WRITE_ACCESS</dt>
</dl>



### -param Data

Pointer to the USHORT data to be transferred.


## -returns



<i>SvgaHwIoPortUshort</i> returns the final status of the operation.




## -remarks



Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">SVGA Functions</a>.)

<i>SvgaHwIoPortUshort</i> intercepts any range access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>OUT DX, AX</b> and <b>IN AX, DX</b>.

If the miniport driver enables the <i>Port</i> range for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUshort</i> function will not be called. Such an application then will have direct access to the I/O port range, unless the miniport driver disables the <i>Port</i> range with another call to <b>VideoSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>IN</b> or <b>OUT</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUshort</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUshort</i> must discard the buffered instructions. Otherwise, it should output them, a USHORT at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUshort</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_emulator_access_entry">EMULATOR_ACCESS_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">SVGA Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pdriver_io_port_ushort_string">SvgaHwIoPortUshortString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsettrappedemulatorports">VideoPortSetTrappedEmulatorPorts</a>
 

 

