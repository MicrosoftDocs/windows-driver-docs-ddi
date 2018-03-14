---
UID: NF:umdprovider.UMDEtwUnregister
title: UMDEtwUnregister function
author: windows-driver-content
description: Unregisters the event trace provider. Call this function before the user-mode driver is unloaded. After this function is called, the driver should not make any other calls to log events.
old-location: display\umdetwunregister.htm
old-project: display
ms.assetid: 19ab8771-2a86-469a-98e4-3d295a458b90
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: UMDEtwUnregister, UMDEtwUnregister function [Display Devices], display.umdetwunregister, umdprovider/UMDEtwUnregister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: umdprovider.h
req.include-header: Umdprovider.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	umdprovider.h
api_name:
-	UMDEtwUnregister
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_SEMANTIC
req.product: Windows 10 or later.
---

# UMDEtwUnregister function


## -description


Unregisters the event trace provider. Call this function before the user-mode driver is unloaded. After this function is called, the driver should not make any other calls to log events.


## -syntax


````
void UMDEtwUnregister(void);
````


## -parameters






## -returns



This function does not return a value.




## -remarks



<b>UMDEtwUnregister</b> is defined inline in Umdprovider.h as:

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>// Registration handle, returned by EventRegister and passed to EventUnregister
__declspec(selectany) REGHANDLE RegHandle = NULL;

FORCEINLINE void UMDEtwUnregister()
{
    EventUnregister(RegHandle);
}</pre>
</td>
</tr>
</table></span></div>
The <a href="https://msdn.microsoft.com/fdcccf6f-2f31-4356-a4ee-3b6229c01b75">EventUnregister</a> function is  described in the <a href="https://msdn.microsoft.com/c10baa8d-50b9-4fda-89d0-d00b1d9f5404">Windows Events</a> documentation.




## -see-also

<a href="..\umdprovider\nf-umdprovider-umdetwregister.md">UMDEtwRegister</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20UMDEtwUnregister function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

