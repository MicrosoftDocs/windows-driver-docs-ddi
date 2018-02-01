---
UID: NS:ntddk._WHEA_NOTIFICATION_DESCRIPTOR
title: "_WHEA_NOTIFICATION_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_NOTIFICATION_DESCRIPTOR structure describes the notification mechanism that is used by an error source.
old-location: whea\whea_notification_descriptor.htm
old-project: whea
ms.assetid: 5b228bb8-dd31-484d-b87a-ec7fed433a4a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "_WHEA_NOTIFICATION_DESCRIPTOR, WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT, Reserved, ErrorThresholdWindowRW, SwitchToPollingThresholdRW, *PWHEA_NOTIFICATION_DESCRIPTOR, WHEA_NOTIFICATION_TYPE_POLLED, WHEA_NOTIFICATION_DESCRIPTOR structure [WHEA Drivers and Applications], ntddk/WHEA_NOTIFICATION_DESCRIPTOR, whea.whea_notification_descriptor, WHEA_NOTIFICATION_TYPE_NMI, ErrorThresholdRW, PollIntervalRW, SwitchToPollingWindowRW, whearef_c2a5ab66-2598-447b-8f5b-d6398c55ff1a.xml, AsUSHORT, WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT, WHEA_NOTIFICATION_TYPE_SCI, WHEA_NOTIFICATION_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	WHEA_NOTIFICATION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PWHEA_NOTIFICATION_DESCRIPTOR, WHEA_NOTIFICATION_DESCRIPTOR"
---

# _WHEA_NOTIFICATION_DESCRIPTOR structure


## -description


The <b>WHEA_NOTIFICATION_DESCRIPTOR</b> structure describes the notification mechanism that is used by an error source.


## -syntax


````
struct WHEA_NOTIFICATION_DESCRIPTOR {
  UCHAR                   Type;
  UCHAR                   Length;
  WHEA_NOTIFICATION_FLAGS Flags;
  union {
    struct {
      ULONG PollInterval;
    } Polled;
    struct {
      ULONG PollInterval;
      ULONG Vector;
      ULONG SwitchToPollingThreshold;
      ULONG SwitchToPollingWindow;
      ULONG ErrorThreshold;
      ULONG ErrorThresholdWindow;
    } Interrupt;
    struct {
      ULONG PollInterval;
      ULONG Vector;
      ULONG SwitchToPollingThreshold;
      ULONG SwitchToPollingWindow;
      ULONG ErrorThreshold;
      ULONG ErrorThresholdWindow;
    } LocalInterrupt;
    struct {
      ULONG PollInterval;
      ULONG Vector;
      ULONG SwitchToPollingThreshold;
      ULONG SwitchToPollingWindow;
      ULONG ErrorThreshold;
      ULONG ErrorThresholdWindow;
    } Sci;
    struct {
      ULONG PollInterval;
      ULONG Vector;
      ULONG SwitchToPollingThreshold;
      ULONG SwitchToPollingWindow;
      ULONG ErrorThreshold;
      ULONG ErrorThresholdWindow;
    } Nmi;
  } u;
};
````


## -struct-fields




### -field u

A union of structures that are specific to each different type of notification mechanism. 


### -field u.Polled

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_POLLED.


### -field u.Polled.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition.


### -field u.Interrupt

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT.


### -field u.Interrupt.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field u.Interrupt.Vector

The interrupt vector for the error source.


### -field u.Interrupt.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field u.Interrupt.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field u.Interrupt.ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field u.Interrupt.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.


### -field u.LocalInterrupt

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT.


### -field u.LocalInterrupt.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field u.LocalInterrupt.Vector

The interrupt vector for the error source.


### -field u.LocalInterrupt.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field u.LocalInterrupt.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field u.LocalInterrupt.ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field u.LocalInterrupt.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.


### -field u.Sci

 A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_SCI.


### -field u.Sci.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field u.Sci.Vector

The interrupt vector for the error source.


### -field u.Sci.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field u.Sci.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field u.Sci.ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field u.Sci.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.


### -field u.Nmi

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_NMI.


### -field u.Nmi.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field u.Nmi.Vector

The interrupt vector for the error source.


### -field u.Nmi.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field u.Nmi.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field u.Nmi.ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field u.Nmi.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.


### -field u.Sea

 


### -field u.Sea.PollInterval

 


### -field u.Sea.Vector

 


### -field u.Sea.SwitchToPollingThreshold

 


### -field u.Sea.SwitchToPollingWindow

 


### -field u.Sea.ErrorThreshold

 


### -field u.Sea.ErrorThresholdWindow

 


### -field u.Sei

 


### -field u.Sei.PollInterval

 


### -field u.Sei.Vector

 


### -field u.Sei.SwitchToPollingThreshold

 


### -field u.Sei.SwitchToPollingWindow

 


### -field u.Sei.ErrorThreshold

 


### -field u.Sei.ErrorThresholdWindow

 


### -field u.Gsiv

 


### -field u.Gsiv.PollInterval

 


### -field u.Gsiv.Vector

 


### -field u.Gsiv.SwitchToPollingThreshold

 


### -field u.Gsiv.SwitchToPollingWindow

 


### -field u.Gsiv.ErrorThreshold

 


### -field u.Gsiv.ErrorThresholdWindow

 


### -field Type

The type of notification mechanism that is used by the error source. This can be one of the following possible values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT"></a><a id="whea_notification_type_externalinterrupt"></a><dl>
<dt><b>WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT</b></dt>
</dl>
</td>
<td width="60%">
The error source notifies the LLHEH for the error source by means of an external interrupt.

</td>
</tr>
<tr>
<td width="40%"><a id="WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT"></a><a id="whea_notification_type_localinterrupt"></a><dl>
<dt><b>WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT</b></dt>
</dl>
</td>
<td width="60%">
The error source notifies the LLHEH for the error source by means of a local interrupt.

</td>
</tr>
<tr>
<td width="40%"><a id="WHEA_NOTIFICATION_TYPE_NMI"></a><a id="whea_notification_type_nmi"></a><dl>
<dt><b>WHEA_NOTIFICATION_TYPE_NMI</b></dt>
</dl>
</td>
<td width="60%">
The error source notifies the LLHEH for the error source by means of a nonmaskable interrupt (NMI).

</td>
</tr>
<tr>
<td width="40%"><a id="WHEA_NOTIFICATION_TYPE_POLLED"></a><a id="whea_notification_type_polled"></a><dl>
<dt><b>WHEA_NOTIFICATION_TYPE_POLLED</b></dt>
</dl>
</td>
<td width="60%">
The low-level hardware error handler (LLHEH)for the error source must periodically poll the error status registers to check for an error condition.

</td>
</tr>
<tr>
<td width="40%"><a id="WHEA_NOTIFICATION_TYPE_SCI"></a><a id="whea_notification_type_sci"></a><dl>
<dt><b>WHEA_NOTIFICATION_TYPE_SCI</b></dt>
</dl>
</td>
<td width="60%">
The error source notifies the LLHEH for the error source by means of a service control interrupt (SCI).

</td>
</tr>
</table> 


### -field Length

The size, in bytes, of the <b>WHEA_NOTIFICATION_DESCRIPTOR</b> structure.


### -field Flags

A WHEA_NOTIFICATION_FLAGS union that indicates which of the members of the <b>WHEA_NOTIFICATION_DESCRIPTOR</b> structure can be written to by the operating system. The WHEA_NOTIFICATION_FLAGS union is defined as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_NOTIFICATION_FLAGS {
  struct {
    USHORT  PollIntervalRW:1;
    USHORT  SwitchToPollingThresholdRW:1;
    USHORT  SwitchToPollingWindowRW:1;
    USHORT  ErrorThresholdRW:1;
    USHORT  ErrorThresholdWindowRW:1;
    USHORT  Reserved:11;
  };
  USHORT  AsUSHORT;
} WHEA_NOTIFICATION_FLAGS, *PWHEA_NOTIFICATION_FLAGS</pre>
</td>
</tr>
</table></span></div><table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="AsUSHORT"></a><a id="asushort"></a><a id="ASUSHORT"></a><dl>
<dt><b><b>AsUSHORT</b></b></dt>
</dl>
</td>
<td width="60%">
A USHORT representation of the contents of the WHEA_NOTIFICATION_FLAGS union.

</td>
</tr>
<tr>
<td width="40%"><a id="ErrorThresholdRW"></a><a id="errorthresholdrw"></a><a id="ERRORTHRESHOLDRW"></a><dl>
<dt><b><b>ErrorThresholdRW</b></b></dt>
</dl>
</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.ErrorThreshold</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>
<td width="40%"><a id="ErrorThresholdWindowRW"></a><a id="errorthresholdwindowrw"></a><a id="ERRORTHRESHOLDWINDOWRW"></a><dl>
<dt><b><b>ErrorThresholdWindowRW</b></b></dt>
</dl>
</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.ErrorThresholdWindow</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>
<td width="40%"><a id="PollIntervalRW"></a><a id="pollintervalrw"></a><a id="POLLINTERVALRW"></a><dl>
<dt><b><b>PollIntervalRW</b></b></dt>
</dl>
</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.PollInterval</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>
<td width="40%"><a id="Reserved"></a><a id="reserved"></a><a id="RESERVED"></a><dl>
<dt><b><b>Reserved</b></b></dt>
</dl>
</td>
<td width="60%">
Reserved for system use.

</td>
</tr>
<tr>
<td width="40%"><a id="SwitchToPollingThresholdRW"></a><a id="switchtopollingthresholdrw"></a><a id="SWITCHTOPOLLINGTHRESHOLDRW"></a><dl>
<dt><b><b>SwitchToPollingThresholdRW</b></b></dt>
</dl>
</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.SwitchToPollingThreshold</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SwitchToPollingWindowRW"></a><a id="switchtopollingwindowrw"></a><a id="SWITCHTOPOLLINGWINDOWRW"></a><dl>
<dt><b><b>SwitchToPollingWindowRW</b></b></dt>
</dl>
</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.SwitchToPollingWindow</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
</table> 


## -remarks


A WHEA_NOTIFICATION_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a> and <a href="..\ntddk\ns-ntddk-_whea_xpf_cmc_descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a> structures.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a>

<a href="..\ntddk\ns-ntddk-_whea_xpf_cmc_descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_NOTIFICATION_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

