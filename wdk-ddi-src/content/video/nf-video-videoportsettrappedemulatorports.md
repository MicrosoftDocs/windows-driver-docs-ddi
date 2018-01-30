---
UID: NF:video.VideoPortSetTrappedEmulatorPorts
title: VideoPortSetTrappedEmulatorPorts function
author: windows-driver-content
description: VGA-compatible (SVGA) miniport drivers call the VideoPortSetTrappedEmulatorPorts function to dynamically change the list of I/O ports that are trapped when a VDM runs in full-screen mode on an x86-based machine.
old-location: display\videoportsettrappedemulatorports.htm
old-project: display
ms.assetid: c1ded22b-a5bf-4755-903a-4797c6a65713
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortSetTrappedEmulatorPorts, VideoPort_Functions_2283311e-a325-433b-9fff-be20e9c0e092.xml, VideoPortSetTrappedEmulatorPorts function [Display Devices], video/VideoPortSetTrappedEmulatorPorts, display.videoportsettrappedemulatorports
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortSetTrappedEmulatorPorts
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
---

# VideoPortSetTrappedEmulatorPorts function


## -description


VGA-compatible (SVGA) miniport drivers call the <b>VideoPortSetTrappedEmulatorPorts</b> function to dynamically change the list of I/O ports that are trapped when a <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VDM</a> runs in full-screen mode on an x86-based machine.


## -syntax


````
VP_STATUS VideoPortSetTrappedEmulatorPorts(
       PVOID               HwDeviceExtension,
       ULONG               NumAccessRanges,
  _In_ PVIDEO_ACCESS_RANGE AccessRange
);
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param NumAccessRanges

Specifies the number of elements in the <i>AccessRange</i> array.


### -param AccessRange [in]

Pointer to an array of <a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a> elements. Each element describes a proper subrange of the <b>EmulatorAccessEntries</b> that the miniport driver set up in <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>. Setting the <b>RangeVisible</b> member of an <i>AccessRange</i> element to <b>TRUE</b> enables direct access to the I/O port range by the full-screen MS-DOS application. Setting a <b>RangeVisible</b> member to <b>FALSE</b> causes application-issued <b>IN</b>s, <b>INSB/INSW/INSD</b>s, <b>OUT</b>s and/or <b>OUTSB/OUTSW/OUTSD</b>s to that range to be trapped and forwarded to the corresponding miniport driver <i>SvgaHwIoPortXxx</i> function for validation.

The <i>AccessRange</i> array passed to <b>VideoPortSetTrappedEmulatorPorts</b> must be a proper subset of the I/O port range(s) that the <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function set up in the <b>EmulatorAccessEntries</b> array of the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> structure. Any I/O port ranges in the access ranges array that are not included in the <b>EmulatorAccessEntries</b> array are trapped and reflected to the user-mode <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VDD</a>.


## -returns


<b>VideoPortSetTrappedEmulatorPorts</b> returns NO_ERROR if it successfully changed the trapped ports. Otherwise, it returns ERROR_INVALID_PARAMETER.



## -remarks


By default, the <i>AccessRange</i> of I/O ports that full-screen MS-DOS applications can access directly includes none of the access range array elements describing I/O port ranges that also have corresponding elements in the <b>EmulatorAccessEntries</b> array of the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> structure. That is, I/O port ranges with corresponding emulator access entries are, by default, hooked to the miniport driver's <i>SvgaHwIoPortXxx</i> functions so application-issued instructions are forwarded to the <i>SvgaHwIoPortXxx</i> functions for validation.

A VGA-compatible SVGA miniport driver can enable and disable ranges of I/O ports on an as-needed basis with calls to <b>VideoPortSetTrappedEmulatorPorts</b>. Enabled port ranges allow a full-screen MS-DOS application to access those I/O ports directly, without having application-issued assembly instructions trapped and forwarded to the miniport driver's <i>SvgaHwIoPortXxx</i> functions for validation first. Direct I/O port access for such an application gives the user faster video I/O response times.

<b>VideoPortSetTrappedEmulatorPorts</b> scans the <i>AccessRange</i> parameter array from the first element to the last, enabling and disabling I/O ports as directed in each element. Note that a range of enabled ports (the <b>RangeVisible</b> member set to <b>TRUE</b>) can be disabled again in the same call if the miniport driver includes a duplicate description of the same range with the <b>RangeVisible</b> member set to <b>FALSE</b>. Note also that a miniport driver can enable a wide range of I/O ports in the initial element of the <i>AccessRange</i> array and selectively disable subranges of ports in subsequent array elements when it calls <b>VideoPortSetTrappedEmulatorPorts</b>.

All full-screen MS-DOS applications use the same IOPM (I/O permission map) in x86-based machines and, therefore, the same set of enabled or disabled I/O ports. On each switch to such a full-screen application, a VGA-compatible miniport driver's <a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a> function is called with the IOCTL_VIDEO_ENABLE_VDM <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a>. The miniport driver should then reinitialize a default set of directly accessible I/O ports, which can include any ports in the <b>EmulatorAccessEntries</b> array.

While giving full-screen MS-DOS applications on x86-based machines direct access to the video ports makes application-initiated video operations faster, every VGA-compatible SVGA miniport driver must continue to trap a subset of critical I/O ports to prevent such an application from hanging the machine. In particular, such miniport drivers should <i>always</i> trap application I/O to the VGA-compatible adapter sequencer and miscellaneous output registers. Such a miniport driver should also trap and validate application-issued direct I/O that could cause the machine to hang for any additional adapter-dependent subset of I/O ports.

Calling <b>VideoPortSetTrappedEmulatorPorts</b> again and resetting the <b>RangeVisible</b> member of an <i>AccessRange</i> element to <b>FALSE</b> causes the application-issued instructions for that range to be forwarded to the corresponding miniport driver <i>SvgaHwIoPortXxx</i> function. 



## -see-also

<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>

<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>

<a href="..\miniport\ns-miniport-_emulator_access_entry.md">EMULATOR_ACCESS_ENTRY</a>

<a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a>

<a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>

<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortSetTrappedEmulatorPorts function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

