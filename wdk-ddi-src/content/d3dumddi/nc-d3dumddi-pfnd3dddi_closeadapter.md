---
UID: NC:d3dumddi.PFND3DDDI_CLOSEADAPTER
title: PFND3DDDI_CLOSEADAPTER
author: windows-driver-content
description: The CloseAdapter function releases resources for a graphics adapter object.
old-location: display\closeadapter.htm
old-project: display
ms.assetid: 9dc7f71a-753d-41ca-8eaa-bff6536e834f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: CloseAdapter, CloseAdapter callback function [Display Devices], PFND3DDDI_CLOSEADAPTER, UserModeDisplayDriver_Functions_ccc1793f-15b1-480f-8835-38326b749308.xml, d3dumddi/CloseAdapter, display.closeadapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	CloseAdapter
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CLOSEADAPTER callback


## -description


The <b>CloseAdapter</b> function releases resources for a graphics adapter object.


## -prototype


````
PFND3DDDI_CLOSEADAPTER CloseAdapter;

__checkReturn HRESULT APIENTRY CloseAdapter(
  _In_ HANDLE hAdapter
)
{ ... }
````


## -parameters




### -param hAdapter [in]

 A handle to the graphics adapter object that was created with the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a> function.


## -returns



<b>CloseAdapter</b> returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result. 




## -remarks



The user-mode display driver's <b>CloseAdapter</b> function should free all of the resources that it allocated for the graphics adapter object.

Before <b>CloseAdapter</b> closes the graphics adapter object, all of the display devices that were created by using the graphics adapter object in calls to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a> function must be destroyed in calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydevice.md">DestroyDevice</a> function.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_adapterfuncs.md">D3DDDI_ADAPTERFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydevice.md">DestroyDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CLOSEADAPTER callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

