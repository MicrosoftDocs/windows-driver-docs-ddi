---
UID: NF:storport.StorPortGetVirtualAddress
title: StorPortGetVirtualAddress function
author: windows-driver-content
description: The StorPortGetVirtualAddress routine obtains a virtual address that maps to the indicated physical address.
old-location: storage\storportgetvirtualaddress.htm
tech.root: storage
ms.assetid: b7091dea-8a29-4ad3-a478-29bc28fd57ef
ms.date: 3/29/2018
ms.keywords: StorPortGetVirtualAddress, StorPortGetVirtualAddress routine [Storage Devices], storage.storportgetvirtualaddress, storport/StorPortGetVirtualAddress, storprt_5245f704-dce0-4683-8510-064ccbb4158c.xml
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
-	StorPortGetVirtualAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetVirtualAddress function


## -description


The <b>StorPortGetVirtualAddress</b> routine obtains a virtual address that maps to the indicated physical address. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param PhysicalAddress [in]

Specifies the physical address to be mapped. This value must have been returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567095">StorPortGetPhysicalAddress</a> and must be from an uncached device extension or SRB extension.


## -returns



<b>StorPortGetVirtualAddress</b> returns a virtual address associated with the physical address indicated in the <i>PhysicalAddress</i> parameter. Typically, this physical address was obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567095">StorPortGetPhysicalAddress</a>. 




## -remarks



The physical address must be an address that is obtained through a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567095">StorPortGetPhysicalAddress</a>.

<b>StorPortGetVirtualAddress</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564643">ScsiPortGetVirtualAddress</a>
 

 

