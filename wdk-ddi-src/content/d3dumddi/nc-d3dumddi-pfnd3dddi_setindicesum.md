---
UID: NC:d3dumddi.PFND3DDDI_SETINDICESUM
title: PFND3DDDI_SETINDICESUM
author: windows-driver-content
description: The SetIndicesUM function sets the current index buffer to the given user memory buffer.
old-location: display\setindicesum.htm
old-project: display
ms.assetid: 9ca38004-8953-4416-8552-c76813192561
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3DDDI_SETINDICESUM, SetIndicesUM, SetIndicesUM callback function [Display Devices], UserModeDisplayDriver_Functions_f692c944-6130-46e3-8e63-f3dbeb051782.xml, d3dumddi/SetIndicesUM, display.setindicesum
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
-	SetIndicesUM
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETINDICESUM callback


## -description


The <i>SetIndicesUM</i> function sets the current index buffer to the given user memory buffer. 


## -prototype


````
PFND3DDDI_SETINDICESUM SetIndicesUM;

__checkReturn HRESULT APIENTRY SetIndicesUM(
  _In_       HANDLE hDevice,
  _In_       UINT   IndexSize,
  _In_ const VOID   *pUMBuffer
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param UINT


### -param *








#### - IndexSize [in]

 The size, in bytes, of the indices that are contained in the index buffer. The value of this parameter is 2 if the indices are 16-bit quantities or 4 if the indices are 32-bit quantities. 


#### - pUMBuffer [in]

 A pointer to the user-memory buffer that supplies the indices for the index buffer.


## -returns



<i>SetIndicesUM</i> returns S_OK or an appropriate error result if the index buffer is not successfully set to the given user memory buffer.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETINDICESUM callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

