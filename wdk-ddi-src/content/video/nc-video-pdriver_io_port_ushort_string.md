---
UID: NC:video.PDRIVER_IO_PORT_USHORT_STRING
title: PDRIVER_IO_PORT_USHORT_STRING
author: windows-driver-content
description: SvgaHwIoPortUshortString traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of USHORT-sized data.
old-location: display\svgahwioportushortstring.htm
old-project: display
ms.assetid: cfb8d6d9-0210-4800-979c-7c6a6bbfe633
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.svgahwioportushortstring, SvgaHwIoPortUshortString callback function [Display Devices], SvgaHwIoPortUshortString, PDRIVER_IO_PORT_USHORT_STRING, PDRIVER_IO_PORT_USHORT_STRING, video/SvgaHwIoPortUshortString, VideoMiniport_Functions_7ac011d5-6b69-4ac5-92dd-abc8f2c43740.xml
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
-	SvgaHwIoPortUshortString
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PDRIVER_IO_PORT_USHORT_STRING callback


## -description


<i>SvgaHwIoPortUshortString</i> traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of USHORT-sized data.


## -prototype


````
PDRIVER_IO_PORT_USHORT_STRING SvgaHwIoPortUshortString;

VP_STATUS SvgaHwIoPortUshortString(
   ULONG_PTR Context,
   ULONG     Port,
   UCHAR     AccessMode,
   PUSHORT   Data,
   ULONG     DataLength
)
{ ... }
````


## -parameters




### -param Context

Specifies the miniport driver-determined context value that was set in <b>EmulatorAccessEntriesContext</b> of VIDEO_PORT_CONFIG_INFO.


### -param Port

Specifies the mapped I/O port to be trapped.


### -param AccessMode

Specifies the type of access allowed, which can be one or a combination (ORed) of the following values:


<dl>
<dt>EMULATOR_READ_ACCESS</dt>
<dt>EMULATOR_WRITE_ACCESS</dt>
</dl>



### -param Data

Pointer to the string of USHORT data values to be transferred. This string is accessed one value at a time until all values have been hooked.


### -param DataLength

Specifies the number of USHORT values in the string.


## -returns



<i>SvgaHwIoPortUshortString</i> returns the final status of the operation.




## -remarks



Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>.)

<i>SvgaHwIoPortUshortString</i> intercepts any range access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>REP OUTSW DX, ESI</b> and <b>REP INSW EDI, DX</b>.

If the miniport driver enables the <i>Port</i> range for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUshortString</i> function will not be called. Such an application then will have direct access to the I/O port range, unless the miniport driver disables the <i>Port</i> range with another call to <b>VideoSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>INSW</b> or <b>OUTSW</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUshortString</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUshortString</i> must discard the buffered instructions. Otherwise, it should output them, a USHORT at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUshortString</i> should be made pageable.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>



<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>



<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



<a href="..\video\nc-video-pdriver_io_port_ushort.md">SvgaHwIoPortUshort</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>



<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDRIVER_IO_PORT_USHORT_STRING callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

