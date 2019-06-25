---
UID: NF:storport.StorPortGetMSIInfo
title: StorPortGetMSIInfo function (storport.h)
description: The StorPortGetMSIInfo routine retrieves the message signaled interrupt (MSI) information for the specified message.
old-location: storage\storportgetmsiinfo.htm
tech.root: storage
ms.assetid: 3c98c04c-246a-42a0-bb40-f7771f7ae968
ms.date: 03/29/2018
ms.keywords: StorPortGetMSIInfo, StorPortGetMSIInfo routine [Storage Devices], storage.storportgetmsiinfo, storport/StorPortGetMSIInfo, storprt_32654460-fd47-4dc9-bd33-2080b881502f.xml
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: Any level.
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortGetMSIInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetMSIInfo function


## -description


The <b>StorPortGetMSIInfo</b> routine retrieves the message signaled interrupt (MSI) information for the specified message. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param MessageId [in]

The identifier of the message for which the information is retrieved.


### -param InterruptInfo [out]

A pointer to a miniport driver-provided <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-_message_interrupt_information">MESSAGE_INTERRUPT_INFORMATION</a> structure that receives the information for the message specified by the <i>MessageId</i> parameter.


## -returns



<b>StorPortGetMSIInfo</b> returns one of the status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the MSI information was successfully received for the specified message.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>HwDeviceExtension</i> passed was <b>NULL</b>.

-or-

The pointer in <i>InterruptInfo</i> for the structure to receive the information is <b>NULL</b>.

-or-

<i>MessageId</i> passed to the function is incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The HBA does not support MSI.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-_message_interrupt_information">MESSAGE_INTERRUPT_INFORMATION</a>
 

 

