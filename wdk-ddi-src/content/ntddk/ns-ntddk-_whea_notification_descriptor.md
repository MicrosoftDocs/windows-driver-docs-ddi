---
UID: NS:ntddk._WHEA_NOTIFICATION_DESCRIPTOR
title: _WHEA_NOTIFICATION_DESCRIPTOR
author: windows-driver-content
description: The WHEA_NOTIFICATION_DESCRIPTOR structure describes the notification mechanism that is used by an error source.
old-location: whea\whea_notification_descriptor.htm
old-project: whea
ms.assetid: 5b228bb8-dd31-484d-b87a-ec7fed433a4a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_NOTIFICATION_DESCRIPTOR, *PWHEA_NOTIFICATION_DESCRIPTOR, WHEA_NOTIFICATION_DESCRIPTOR
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
req.alt-api: WHEA_NOTIFICATION_DESCRIPTOR
req.alt-loc: Ntddk.h
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
req.typenames: *PWHEA_NOTIFICATION_DESCRIPTOR, WHEA_NOTIFICATION_DESCRIPTOR
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

### -field Type

The type of notification mechanism that is used by the error source. This can be one of the following possible values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT

</td>
<td width="60%">
The error source notifies the LLHEH for the error source by means of an external interrupt.

</td>
</tr>
<tr>

### -field WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT

</td>
<td width="60%">
The error source notifies the LLHEH for the error source by means of a local interrupt.

</td>
</tr>
<tr>

### -field WHEA_NOTIFICATION_TYPE_NMI

</td>
<td width="60%">
The error source notifies the LLHEH for the error source by means of a nonmaskable interrupt (NMI).

</td>
</tr>
<tr>

### -field WHEA_NOTIFICATION_TYPE_POLLED

</td>
<td width="60%">
The low-level hardware error handler (LLHEH)for the error source must periodically poll the error status registers to check for an error condition.

</td>
</tr>
<tr>

### -field WHEA_NOTIFICATION_TYPE_SCI

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
</table></span></div>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field AsUSHORT

</td>
<td width="60%">
A USHORT representation of the contents of the WHEA_NOTIFICATION_FLAGS union.

</td>
</tr>
<tr>

### -field ErrorThresholdRW

</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.ErrorThreshold</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>

### -field ErrorThresholdWindowRW

</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.ErrorThresholdWindow</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>

### -field PollIntervalRW

</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.PollInterval</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>

### -field Reserved

</td>
<td width="60%">
Reserved for system use.

</td>
</tr>
<tr>

### -field SwitchToPollingThresholdRW

</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.SwitchToPollingThreshold</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
<tr>

### -field SwitchToPollingWindowRW

</td>
<td width="60%">
A single bit that indicates that the operating system can write to the <b>u.</b><i>xxx</i><b>.SwitchToPollingWindow</b> members of the WHEA_NOTIFICATION_DESCRIPTOR structure.

</td>
</tr>
</table>
 


### -field u

A union of structures that are specific to each different type of notification mechanism. 


### -field Polled

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_POLLED.


### -field PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition.

</dd>
</dl>

### -field Interrupt

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT.


### -field PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field Vector

The interrupt vector for the error source.


### -field SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.

</dd>
</dl>

### -field LocalInterrupt

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT.


### -field PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field Vector

The interrupt vector for the error source.


### -field SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.

</dd>
</dl>

### -field Sci

 A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_SCI.


### -field PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field Vector

The interrupt vector for the error source.


### -field SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.

</dd>
</dl>

### -field Nmi

A structure that describes the notification mechanism when the <b>Type</b> member is set to WHEA_NOTIFICATION_TYPE_NMI.


### -field PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.


### -field Vector

The interrupt vector for the error source.


### -field SwitchToPollingThreshold

The number of errors that must occur within the time specified by the <b>SwitchToPollingWindow</b> member before the error source is switched to polling mode.


### -field SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the <b>SwitchToPollingThreshold</b> member must occur before the error source is switched to polling mode.


### -field ErrorThreshold

The number of errors that must occur within the time specified by the <b>ErrorThresholdWindow</b> member before an error from the error source is processed by the operating system.


### -field ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the <b>ErrorThreshold</b> member must occur before an error from the error source is processed by the operating system.

</dd>
</dl>
</dd>
</dl>

## -remarks
A WHEA_NOTIFICATION_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a> and <a href="..\ntddk\ns-ntddk-_whea_xpf_cmc_descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a> structures.


## -see-also
<dl>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_cmc_descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_NOTIFICATION_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

