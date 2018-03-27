---
UID: NF:wdfrequest.WDF_REQUEST_SEND_OPTIONS_INIT
title: WDF_REQUEST_SEND_OPTIONS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS_INIT function initializes a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_init.htm
old-project: wdf
ms.assetid: 65e57147-f8a1-4b9b-b856-51f89bcba149
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_9a31e96a-4cb1-43ea-b429-591f820838d8.xml, WDF_REQUEST_SEND_OPTIONS_INIT, WDF_REQUEST_SEND_OPTIONS_INIT function, kmdf.wdf_request_send_options_init, wdf.wdf_request_send_options_init, wdfrequest/WDF_REQUEST_SEND_OPTIONS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfrequest.h
api_name:
-	WDF_REQUEST_SEND_OPTIONS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_SEND_OPTIONS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -parameters




### -param Options [out]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure.


### -param Flags [in]

A bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552493">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>-typed flags. 


## -returns



None




## -remarks



The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure, sets the structure's <b>Size</b> member, and sets the <b>Flag</b> member to the specified <i>Flags</i> value.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_REQUEST_SEND_OPTIONS options;
BOOLEAN ret;

WDF_REQUEST_SEND_OPTIONS_INIT(
                              &amp;options,
                              WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET
                              );

ret = WdfRequestSend(
                     Request,
                     Target,
                     &amp;options
                     );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552493">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552498">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

