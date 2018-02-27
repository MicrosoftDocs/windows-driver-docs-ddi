---
UID: NF:storport.StorPortGetActivityIdSrb
title: StorPortGetActivityIdSrb function
author: windows-driver-content
description: Retrieves the Event Tracing for Windows (ETW) activity ID associated with a request block.
old-location: storage\storportgetactivityidsrb.htm
old-project: storage
ms.assetid: 63E956F5-C87C-45AA-BE16-2AD07F3BA050
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortGetActivityIdSrb, StorPortGetActivityIdSrb routine [Storage Devices], storage.storportgetactivityidsrb, storport/StorPortGetActivityIdSrb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: Any
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortGetActivityIdSrb
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetActivityIdSrb function


## -description


Retrieves the Event Tracing for Windows (ETW) activity ID associated with a request block.


## -syntax


````
ULONG StorPortGetActivityIdSrb(
  _In_  PVOID               HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK Srb,
  _Out_ LPGUID              ActivityId
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The request block to retrieve the ETW activity ID for.


### -param ActivityId [out]

A pointer to a caller-supplied GUID to receive the ETW activity ID.


## -returns



A status value indicating the result of the notification. This can be one of these values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The ETW activity ID was returned in <i>ActivityId</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer in <i>ActivityId</i> or <i>Srb</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
An ETW activity ID is not associated with the request in <i>Srb</i>.

</td>
</tr>
</table>
 



