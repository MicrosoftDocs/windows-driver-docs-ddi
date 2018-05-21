---
UID: NF:storport.StorPortGetPfns
title: StorPortGetPfns function
author: windows-driver-content
description: The StorPortGetPfns routine can be called when a miniport needs to retreive PFNs associated with a MDL for a SRB.
old-location: storage\storportgetpfns.htm
old-project: storage
ms.assetid: F9E69501-4889-4A1B-8942-C6D4406474DE
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortGetPfns, StorPortGetPfns routine [Storage Devices], storage.storportgetpfns, storport/StorPortGetPfns
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Storport.h
api_name:
-	StorPortGetPfns
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetPfns function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>StorPortGetPfns</b> routine can be called when a miniport needs to retreive PFNs associated with a MDL for a SRB



## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver.


### -param Srb [in]

A pointer to the source SCSI request block (SRB). 


### -param Mdl [in]

A pointer to the MDL for which Pfns are requested. Only MDLs obtained 
            using <b>StorPortGetOriginalMdl</b> or <b>StorPortGetDataInBufferMdl</b> are supported.


### -param Pfns [out]

 A pointer to the beginning of the array of physical page numbers that are associated with the MDL.
              Callers must NOT modify or update or free the list.


### -param PfnCount [out]

Specifies the number of PFNs in the array.


### -param StartingOffset [out]

Specifies the byte offset within the initial page of the buffer described by the given MDL.


## -returns



<b>StorPortGetPfns</b> returns one of the following status codes:

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
The list items were removed successfully or the list is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer to one of the parameters  is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



 Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the device object for the HBA immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj553718">StorPortGetDataInBufferMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567093">StorPortGetOriginalMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>
 

 

