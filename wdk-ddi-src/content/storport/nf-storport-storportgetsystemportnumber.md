---
UID: NF:storport.StorPortGetSystemPortNumber
title: StorPortGetSystemPortNumber function
author: windows-driver-content
description: The StorPortGetSystemPortNumber routine retrieves the system assigned port number for a storage adapter.
old-location: storage\storportgetsystemportnumber.htm
old-project: storage
ms.assetid: D1205C85-6F23-4D08-A146-2FA8C00FD6E9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortGetSystemPortNumber, StorPortGetSystemPortNumber routine [Storage Devices], storage.storportgetsystemportnumber, storport/StorPortGetSystemPortNumber
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortGetSystemPortNumber
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetSystemPortNumber function


## -description


The <b>StorPortGetSystemPortNumber</b> routine retrieves the system assigned port number for a storage adapter.


## -syntax


````
ULONG StorPortGetSystemPortNumber(
  _In_    PVOID         HwDeviceExtension,
  _Inout_ PSTOR_ADDRESS Address
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in, out]

A pointer to a storage address structure formatted as <a href="..\storport\ns-storport-_stor_addr_btl8.md">STOR_ADDR_BTL8</a>. On return, the <b>Port</b> member of this structure will contain the port value assigned to the adapter.


## -returns



<b>StorPortGetSystemPortNumber</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
A port number value is not yet assigned to the storage adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that port number of the  storage adapter was returned successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> was <b>NULL</b>.

-or-

The <b>Type</b> member of <i>Address</i> is not <b>STOR_ADDRESS_TYPE_BTL8</b>.

</td>
</tr>
</table>
 




## -remarks



The address structure pointed to by <i>Address</i> is allocated and formatted as <a href="..\storport\ns-storport-_stor_addr_btl8.md">STOR_ADDR_BTL8</a>. The <b>Type</b> member of <i>Address</i> must be set to <b>STOR_ADDRESS_TYPE_BTL8</b> and the <b>Length</b> member <i>Address</i> must be greater than or equal to <b>STOR_ADDR_BTL8_ADDRESS_LENGTH</b>.




## -see-also

<a href="..\storport\ns-storport-_stor_address.md">STOR_ADDRESS</a>



<a href="..\storport\ns-storport-_stor_addr_btl8.md">STOR_ADDR_BTL8</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetSystemPortNumber routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

