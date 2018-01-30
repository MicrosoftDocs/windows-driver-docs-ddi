---
UID: NC:video.PDRIVER_IO_PORT_UCHAR
title: PDRIVER_IO_PORT_UCHAR
author: windows-driver-content
description: SvgaHwIoPortUchar traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending UCHAR-sized data.
old-location: display\svgahwioportuchar.htm
old-project: display
ms.assetid: 91e2dc51-0f3a-4cda-abe6-72893fd4da79
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.svgahwioportuchar, SvgaHwIoPortUchar callback function [Display Devices], SvgaHwIoPortUchar, PDRIVER_IO_PORT_UCHAR, PDRIVER_IO_PORT_UCHAR, video/SvgaHwIoPortUchar, VideoMiniport_Functions_d926584b-82e3-463e-ad50-b04d065a1d9d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	video.h
apiname:
-	SvgaHwIoPortUchar
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PDRIVER_IO_PORT_UCHAR callback


## -description


<i>SvgaHwIoPortUchar</i> traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending UCHAR-sized data.


## -prototype


````
PDRIVER_IO_PORT_UCHAR SvgaHwIoPortUchar;

VP_STATUS SvgaHwIoPortUchar(
   ULONG_PTR Context,
   ULONG     Port,
   UCHAR     AccessMode,
   PUCHAR    Data
)
{ ... }
````


## -parameters




### -param Context

Specifies the miniport driver-defined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>.


### -param Port

Specifies the mapped I/O port to be trapped.


### -param AccessMode

Specifies the type of access to be trapped, which can be one or a combination (ORed) of the following values:


<dl>
<dt>EMULATOR_READ_ACCESS</dt>
<dt>EMULATOR_WRITE_ACCESS</dt>
</dl>



### -param Data

Pointer to the byte to be transferred.


## -returns


<i>SvgaHwIoPortUchar</i> returns the final status of the operation.



## -remarks


Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>.)

<i>SvgaHwIoPortUchar</i> intercepts any byte access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>OUT DX, AL</b> and <b>IN AL, DX</b>.

If the miniport driver enables the <i>Port</i> for direct access by calling <a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>, its <i>SvgaHwIoPortUchar</i> function will not be called. Such an application then will have direct access to the <i>Port</i>, unless the miniport driver disables the <i>Port</i> with another call to <b>VideoPortSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>IN</b> or <b>OUT</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUchar</i> must buffer subsequent instructions from the application to the <i>Port</i> and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUchar</i> must discard the buffered instructions. Otherwise, it should output them, a UCHAR at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUchar</i> should be made pageable.



## -see-also

<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>

<a href="..\miniport\ns-miniport-_emulator_access_entry.md">EMULATOR_ACCESS_ENTRY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>

<a href="..\video\nc-video-pdriver_io_port_uchar_string.md">SvgaHwIoPortUcharString</a>

<a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>

<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDRIVER_IO_PORT_UCHAR callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

