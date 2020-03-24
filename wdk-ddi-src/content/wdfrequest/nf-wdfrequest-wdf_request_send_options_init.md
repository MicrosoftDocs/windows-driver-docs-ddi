---
UID: NF:wdfrequest.WDF_REQUEST_SEND_OPTIONS_INIT
title: WDF_REQUEST_SEND_OPTIONS_INIT function (wdfrequest.h)
description: The WDF_REQUEST_SEND_OPTIONS_INIT function initializes a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_init.htm
tech.root: wdf
ms.assetid: 65e57147-f8a1-4b9b-b856-51f89bcba149
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_SEND_OPTIONS_INIT function"]
ms.keywords: DFRequestObjectRef_9a31e96a-4cb1-43ea-b429-591f820838d8.xml, WDF_REQUEST_SEND_OPTIONS_INIT, WDF_REQUEST_SEND_OPTIONS_INIT function, kmdf.wdf_request_send_options_init, wdf.wdf_request_send_options_init, wdfrequest/WDF_REQUEST_SEND_OPTIONS_INIT
f1_keywords:
 - "wdfrequest/WDF_REQUEST_SEND_OPTIONS_INIT"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfrequest.h
api_name:
- WDF_REQUEST_SEND_OPTIONS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_REQUEST_SEND_OPTIONS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -parameters




### -param Options [out]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.


### -param Flags [in]

A bitwise OR of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_send_options_flags">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>-typed flags. 


## -remarks



The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure, sets the structure's <b>Size</b> member, and sets the <b>Flag</b> member to the specified <i>Flags</i> value.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>.

```cpp
WDF_REQUEST_SEND_OPTIONS options;
BOOLEAN ret;

WDF_REQUEST_SEND_OPTIONS_INIT(
                              &options,
                              WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET
                              );

ret = WdfRequestSend(
                     Request,
                     Target,
                     &options
                     );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_send_options_flags">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_send_options_set_timeout">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a>
 

 

