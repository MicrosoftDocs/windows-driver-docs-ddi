---
UID: NC:video.PDRIVER_IO_PORT_ULONG_STRING
title: PDRIVER_IO_PORT_ULONG_STRING (video.h)
description: SvgaHwIoPortUlongString traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of ULONG-sized data.
old-location: display\svgahwioportulongstring.htm
tech.root: display
ms.assetid: 190adc75-7274-49e2-a9b6-2897168df091
ms.date: 05/10/2018
ms.keywords: PDRIVER_IO_PORT_ULONG_STRING, PDRIVER_IO_PORT_ULONG_STRING callback, SvgaHwIoPortUlongString, SvgaHwIoPortUlongString callback function [Display Devices], VideoMiniport_Functions_107f011d-c8c7-4f9f-ac81-4d0b33caa3da.xml, display.svgahwioportulongstring, video/SvgaHwIoPortUlongString
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	SvgaHwIoPortUlongString
product:
- Windows
targetos: Windows
req.typenames: 
---

# PDRIVER_IO_PORT_ULONG_STRING callback function


## -description


<i>SvgaHwIoPortUlongString</i> traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of ULONG-sized data.


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

Pointer to the ULONG data string to be transferred. The string is hooked out one value at a time until it is all used.


### -param DataLength

Specifies the number of ULONG values in the string.


## -returns



<i>SvgaHwIoPortUlongString</i> returns the final status of the operation.




## -remarks



Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>.)

<i>SvgaHwIoPortUlongString</i> intercepts any range access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>REP OUTSD DX, ESI</b> and <b>REP INSD EDI, DX</b>.

If the miniport driver enables the <i>Port</i> range for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUlongString</i> function will not be called. Such an application then will have direct access to the I/O port range, unless the miniport driver disables the <i>Port</i> range with another call to <b>VideoSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>INSD</b> or <b>OUTSD</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUlongString</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUlongString</i> must discard the buffered instructions. Otherwise, it should output them, a ULONG at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUlongString</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564131">EMULATOR_ACCESS_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>



<a href="https://msdn.microsoft.com/e749188f-a255-403a-8ae9-a2c3c9b41c58">SvgaHwIoPortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570366">VideoPortSetTrappedEmulatorPorts</a>
 

 

