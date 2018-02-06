---
UID: NC:dispmprt.DXGKDDI_UNLOAD
title: DXGKDDI_UNLOAD
author: windows-driver-content
description: The DxgkDdiUnload function frees any resources allocated during execution of the display miniport driver's DriverEntry function.
old-location: display\dxgkddiunload.htm
old-project: display
ms.assetid: 336fa87a-6c3e-4337-90d9-b0ebeb355e68
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiunload, DxgkDdiUnload callback function [Display Devices], DxgkDdiUnload, DXGKDDI_UNLOAD, DXGKDDI_UNLOAD, dispmprt/DxgkDdiUnload, DmFunctions_b7f60489-c7e7-4bd1-bf17-ff193bc7d614.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dispmprt.h
apiname:
-	DxgkDdiUnload
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---

# DXGKDDI_UNLOAD callback


## -description


The <i>DxgkDdiUnload</i> function frees any resources allocated during execution of the display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


## -prototype


````
DXGKDDI_UNLOAD DxgkDdiUnload;

VOID DxgkDdiUnload(
   VOID 
)
{ ... }
````


## -parameters










## -returns


This callback function does not return a value.



## -remarks


Typically, there will be nothing to do in <i>DxgkDdiUnload</i>.

<i>DxgkDdiUnload</i> should be made pageable.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_UNLOAD callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

