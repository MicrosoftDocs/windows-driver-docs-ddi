---
UID: NF:storport.StorPortGetRequestInfo
title: StorPortGetRequestInfo function
author: windows-driver-content
description: The StorPortGetRequestInfo routine retrieves the IO request information associated with a SCSI request block (SRB) and returns it in a STOR_REQUEST_INFO structure.
old-location: storage\storportgetrequestinfo.htm
tech.root: storage
ms.assetid: 3B0A25E8-6DBC-4AA9-A0D0-DDB36B402F43
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortGetRequestInfo, StorPortGetRequestInfo routine [Storage Devices], storage.storportgetrequestinfo, storport/StorPortGetRequestInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortGetRequestInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetRequestInfo function


## -description



   The <b>StorPortGetRequestInfo</b> routine retrieves the IO request information associated with a SCSI request block (SRB) and  returns it in a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451524">STOR_REQUEST_INFO</a> structure. 
  


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

A pointer to the SRB to be queried.


### -param RequestInfo [out]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/hh451524">STOR_REQUEST_INFO</a> structure.


## -returns



The <b>StorPortGetRequestInfo</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUPPORTED_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The version specified for <a href="https://msdn.microsoft.com/library/windows/hardware/hh451524">STOR_REQUEST_INFO</a> is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>Srb</i> or <i>RequestInfo</i> is set to NULL.

</td>
</tr>
</table>
 




## -remarks



The caller of <b>StorPortGetRequestInfo</b> must set the <b>Version</b> member of <i>RequestInfo</i> to STOR_REQUEST_INFO_VER_1. Otherwise, function will return STOR_STATUS_UNSUPPORTED_VERSION.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451524">STOR_REQUEST_INFO</a>
 

 

