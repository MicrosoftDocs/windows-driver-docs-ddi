---
UID: NC:video.PDRIVER_IO_PORT_UCHAR
title: PDRIVER_IO_PORT_UCHAR (video.h)
description: SvgaHwIoPortUchar traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending UCHAR-sized data.
old-location: display\svgahwioportuchar.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PDRIVER_IO_PORT_UCHAR callback function"]
ms.keywords: PDRIVER_IO_PORT_UCHAR, PDRIVER_IO_PORT_UCHAR callback, SvgaHwIoPortUchar, SvgaHwIoPortUchar callback function [Display Devices], VideoMiniport_Functions_d926584b-82e3-463e-ad50-b04d065a1d9d.xml, display.svgahwioportuchar, video/SvgaHwIoPortUchar
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PDRIVER_IO_PORT_UCHAR
 - video/PDRIVER_IO_PORT_UCHAR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - SvgaHwIoPortUchar
---

# PDRIVER_IO_PORT_UCHAR callback function


## -description

<i>SvgaHwIoPortUchar</i> traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending UCHAR-sized data.

## -parameters

### -param Context

Specifies the miniport driver-defined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>.

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

Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="/windows-hardware/drivers/ddi/index">SVGA Functions</a>.)

<i>SvgaHwIoPortUchar</i> intercepts any byte access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>OUT DX, AL</b> and <b>IN AL, DX</b>.

If the miniport driver enables the <i>Port</i> for direct access by calling <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportsettrappedemulatorports">VideoPortSetTrappedEmulatorPorts</a>, its <i>SvgaHwIoPortUchar</i> function will not be called. Such an application then will have direct access to the <i>Port</i>, unless the miniport driver disables the <i>Port</i> with another call to <b>VideoPortSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>IN</b> or <b>OUT</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUchar</i> must buffer subsequent instructions from the application to the <i>Port</i> and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUchar</i> must discard the buffered instructions. Otherwise, it should output them, a UCHAR at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUchar</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/miniport/ns-miniport-_emulator_access_entry">EMULATOR_ACCESS_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/index">SVGA Functions</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pdriver_io_port_uchar_string">SvgaHwIoPortUcharString</a>



<a href="/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a>



<a href="/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportsettrappedemulatorports">VideoPortSetTrappedEmulatorPorts</a>
