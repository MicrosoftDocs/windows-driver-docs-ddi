---
UID: NF:ufxclient.UFX_ENDPOINT_CALLBACKS_INIT
title: UFX_ENDPOINT_CALLBACKS_INIT function (ufxclient.h)
description: The UFX_ENDPOINT_CALLBACKS_INIT macro initializes the UFX_ENDPOINT_CALLBACKS structure.
old-location: buses\ufx_endpoint_callbacks_init.htm
tech.root: usbref
ms.assetid: 10EB0C86-915F-4C24-ADBE-1D8E8DD8ECB6
ms.date: 05/07/2018
ms.keywords: UFX_ENDPOINT_CALLBACKS_INIT, UFX_ENDPOINT_CALLBACKS_INIT function [Buses], buses.ufx_endpoint_callbacks_init, ufxclient/UFX_ENDPOINT_CALLBACKS_INIT
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
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
req.lib: ufxstub.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ufxclient.h
api_name:
-	UFX_ENDPOINT_CALLBACKS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UFX_ENDPOINT_CALLBACKS_INIT function


## -description


The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure.<div class="alert"><b>Note</b>  <p class="note">Note that there are currently no endpoint callback functions defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure. 

</div>
<div> </div>



## -parameters




### -param Callbacks [out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure.


## -returns



This function does not return a value.




## -remarks



The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro will set all fields of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure to zero and set the size field appropriately.

<div class="alert"><b>Note</b>  Note that there are currently no endpoint callback functions defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure. </div>
<div> </div>


