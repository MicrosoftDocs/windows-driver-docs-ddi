---
UID: NC:usbbusif.PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB
title: PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB
author: windows-driver-content
description: This callback function is not supported.The SubmitIsoOutUrb function submits a USB request block (URB) directly to the bus driver without requiring the allocation of an IRP.
old-location: buses\submitisoouturb.htm
old-project: usbref
ms.assetid: cc8996e5-e10d-463b-91e3-6ef56d3fa32a
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB, PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB callback, SubmitIsoOutUrb, SubmitIsoOutUrb callback function [Buses], buses.submitisoouturb, usbbusif/SubmitIsoOutUrb, usbinterKR_7caf9f1e-d3e3-4d26-b91f-c2864594703a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
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
req.irql: ANY
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbbusif.h
api_name:
-	SubmitIsoOutUrb
product: Windows
targetos: Windows
req.typenames: 
---

# PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB callback function


## -description


This callback function is not supported.

The <i>SubmitIsoOutUrb</i> function submits a USB request block (URB) directly to the bus driver without requiring the allocation of an IRP. 


## -parameters












#### - BusContext [in]

Handle returned in the <i>BusContext</i> member of the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff539210">USB_BUS_INTERFACE_USBDI_V0</a> structure by an IRP_MN_QUERY_INTERFACE request. 


#### - Urb [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> to be passed to the port driver. 


## -returns



<b>SubmitIsoOutUrb</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Fast isochronous interfaces and real-time threads are not supported by the host controller. 

</td>
</tr>
</table>
 




## -remarks



This function replaces the <b>USBD_BusSubmitIsoOutUrb</b> library function provided by <i>usbd.sys</i>. 

This function allows clients running in real-time threads at an elevated IRQL to have rapid access to the bus driver. This USB host controller must support real-time threads for this function to work. 

The calling driver forfeits any packet-level error information when calling this function. 

The function definition that is provided on this reference page is an example routine whose parameters are just placeholder names. The actual prototype of this function is declared in <i>usbbusif.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB) (
    IN PVOID,
    IN PURB</pre>
</td>
</tr>
</table></span></div>
  );



