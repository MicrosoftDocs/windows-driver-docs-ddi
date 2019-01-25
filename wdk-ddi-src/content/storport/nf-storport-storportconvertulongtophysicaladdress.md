---
UID: NF:storport.StorPortConvertUlongToPhysicalAddress
title: StorPortConvertUlongToPhysicalAddress function (storport.h)
description: The StorPortConvertUlongToPhysicalAddress routine converts an unsigned long address into a physical address.
old-location: storage\storportconvertulongtophysicaladdress.htm
tech.root: storage
ms.assetid: 772ca60b-a957-47de-b95d-486497b295ce
ms.date: 03/29/2018
ms.keywords: StorPortConvertUlongToPhysicalAddress, StorPortConvertUlongToPhysicalAddress routine [Storage Devices], storage.storportconvertulongtophysicaladdress, storport/StorPortConvertUlongToPhysicalAddress, storprt_c0da13f0-81f8-48ae-93e2-8af7bcedf4dc.xml
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortConvertUlongToPhysicalAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortConvertUlongToPhysicalAddress function


## -description


The <b>StorPortConvertUlongToPhysicalAddress</b> routine converts an unsigned long address into a physical address.


## -parameters




### -param UlongAddress [in]

Contains the address to be converted.


## -returns



The <b>StorPortConvertUlongToPhysicalAddress</b> routine returns the physical address that corresponds to the unsigned long address that the caller passed in.




## -remarks



<b>StorPortConvertUlongToPhysicalAddress</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef PHYSICAL_ADDRESS STOR_PHYSICAL_ADDRESS, *PSTOR_PHYSICAL_ADDRESS;
</pre>
</td>
</tr>
</table></span></div>
The <b>STOR_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that Storport miniport drivers use to represent either a physical addresses or a bus-relative address. 

The StorPortConvertPhysicalAddressToULong64 macro converts a physical address to a ULONG64 value.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>ULONG64 StorPortConvertPhysicalAddressToULong64(
  [in] STOR_PHYSICAL_ADDRESS Address
);
</pre>
</td>
</tr>
</table></span></div>


<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="Address__in_"></a><a id="address__in_"></a><a id="ADDRESS__IN_"></a><i>Address [in]</i>

</td>
<td width="60%">
<b>STOR_PHYSICAL_ADDRESS</b>

Specifies an address value of type STOR_PHYSICAL_ADDRESS.

</td>
</tr>
<tr>
<td width="40%">
<a id="Return_value"></a><a id="return_value"></a><a id="RETURN_VALUE"></a>Return value

</td>
<td width="60%">
<b>ULONG64</b>

<b>StorPortConvertPhysicalAddressToULong64</b> returns a ULONG64 value derived from the physical address that was passed to it.

</td>
</tr>
</table>
 

StorPortConvertPhysicalAddressToULong64 uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.



