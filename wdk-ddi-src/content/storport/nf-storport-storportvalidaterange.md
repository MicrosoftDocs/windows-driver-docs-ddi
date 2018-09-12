---
UID: NF:storport.StorPortValidateRange
title: StorPortValidateRange function
author: windows-driver-content
description: The StorPortValidateRange routine determines whether a specified range of I/O addresses is in use by another adapter. This routine is obsolete in Windows NT 4.0 and later operating systems.
old-location: storage\storportvalidaterange.htm
tech.root: storage
ms.assetid: 505d6986-c59d-46b3-8437-29fc6a808ccd
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortValidateRange, StorPortValidateRange routine [Storage Devices], storage.storportvalidaterange, storport/StorPortValidateRange, storprt_7d3583a5-211d-414e-880d-31c04145d3ab.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortDeprecated
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
-	StorPortValidateRange
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortValidateRange function


## -description


The <b>StorPortValidateRange</b> routine determines whether a specified range of I/O addresses is in use by another adapter. This routine is obsolete in Windows NT 4.0 and later operating systems. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param BusType [in]

Contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566356">STORAGE_BUS_TYPE</a> that indicates the bus type. 


### -param SystemIoBusNumber

<p>Contains an integer identifying a system bus.</p>


### -param IoAddress [in]

Contains the beginning address of the range of addresses to be validated. 


### -param NumberOfBytes [in]

Contains the length in bytes of the range of addresses to be validated. 


### -param InIoSpace [in]

Indicates, when <b>TRUE</b>, that the address range is in I/O space. If <b>FALSE</b>, the address is in memory space. 


#### - SystemToBusNumber [in]

Contains an integer identifying a system bus.


## -returns



<b>StorPortValidateRange</b> returns <b>TRUE</b> if a specified range of addresses is not claimed by another driver. This routine returns <b>FALSE</b> if another driver has claimed the address range. 




## -remarks



For compatibility with older versions of Windows, this routine always returns <b>TRUE</b>.

 Miniport drivers are given valid I/O ranges in the <b>AccessRanges</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a> structure when the Storport driver calls the miniport's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> callback routine.

<b>StorPortValidateRange</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent bus-relative addresses.

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




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564761">ScsiPortValidateRange</a>
 

 

