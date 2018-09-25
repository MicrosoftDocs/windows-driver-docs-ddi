---
UID: NC:sercx.EVT_SERCX_PURGE
title: EVT_SERCX_PURGE
author: windows-driver-content
description: The EvtSerCxPurge event callback function is called by the serial framework extension (SerCx) to purge the serial controller's hardware buffers.
old-location: serports\evtsercxpurge.htm
tech.root: serports
ms.assetid: 036D9AAC-C740-4108-B952-0A4F91585488
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: 1/EvtSerCxPurge, EVT_SERCX_PURGE, EVT_SERCX_PURGE callback, EvtSerCxPurge, EvtSerCxPurge callback function [Serial Ports], serports.evtsercxpurge
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	1.0\Sercx.h
api_name:
-	EvtSerCxPurge
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX_PURGE callback function


## -description


The <i>EvtSerCxPurge</i> event callback function is called by the serial framework extension (SerCx) to purge the serial controller's hardware buffers.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param PurgeMask [in]

A set of flags that describe the hardware buffers that are to be purged.  Currently, no flags are defined for purge operations that are performed by the serial controller. For more information, see Remarks.


## -returns



The <i>EvtSerCxPurge</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



The serial controller driver implements this callback function. SerCx calls this function when a client (application or peripheral driver) sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546655">IOCTL_SERIAL_PURGE</a> control request that requires hardware buffers managed by the serial controller to be purged.

SerCx performs the purge operations that are designated by the flags listed in the following table.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>SERIAL_PURGE_RXABORT</td>
<td>Purge all read requests.</td>
</tr>
<tr>
<td>SERIAL_PURGE_RXCLEAR</td>
<td>Purge the input buffer, if one exists. Any receive data in this buffer is discarded.</td>
</tr>
<tr>
<td>SERIAL_PURGE_TXABORT</td>
<td>Purge all write requests.</td>
</tr>
<tr>
<td>SERIAL_PURGE_TXCLEAR</td>
<td>Purge the output buffer, if one exists. Any transmit data in this buffer is discarded.</td>
</tr>
</table>
 

The <i>EvtSerCxPurge</i> function will never receive a purge request that contains any of the flags in this table. The SERIAL_PURGE_<i>XXX</i> flags are defined in the Ntddser.h header file.

Currently, no SERIAL_PURGE_<i>XXX</i> flags are defined to designate purge operations that are performed by the serial controller driver, and the serial controller driver should perform no purge operations in response to a <i>EvtSerCxPurge</i> call.

If the <b>IOCTL_SERIAL_PURGE</b> control request requires pending read or write requests to be canceled, SerCx cancels these requests before it calls the <i>EvtSerCxPurge</i> function.

To register an <i>EvtSerCxPurge</i> callback function, the controller driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method during the <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  EVT_SERCX_PURGE(
    __in WDFDEVICE Device,
    __in ULONG PurgeMask
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxPurge</i> callback function that is named <code>MyEvtSerCxPurge</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_PURGE MyEvtSerCxPurge;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
  MyEvtSerCxPurge(
    __in WDFDEVICE Device,
    __in ULONG PurgeMask
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546655">IOCTL_SERIAL_PURGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a>
 

 

