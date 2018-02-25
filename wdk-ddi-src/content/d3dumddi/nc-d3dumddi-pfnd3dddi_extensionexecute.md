---
UID: NC:d3dumddi.PFND3DDDI_EXTENSIONEXECUTE
title: PFND3DDDI_EXTENSIONEXECUTE
author: windows-driver-content
description: The ExtensionExecute function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.
old-location: display\extensionexecute.htm
old-project: display
ms.assetid: a3f73651-bfff-48fa-aa61-477b8af7fa07
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ExtensionExecute, ExtensionExecute callback function [Display Devices], PFND3DDDI_EXTENSIONEXECUTE, UserModeDisplayDriver_Functions_2972e743-bdb5-41ab-92ff-986b8335883b.xml, d3dumddi/ExtensionExecute, display.extensionexecute
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
-	ExtensionExecute
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_EXTENSIONEXECUTE callback


## -description


The <i>ExtensionExecute</i> function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.


## -prototype


````
PFND3DDDI_EXTENSIONEXECUTE ExtensionExecute;

__checkReturn HRESULT APIENTRY ExtensionExecute(
  _In_       HANDLE                     hDevice,
  _In_ const D3DDDIARG_EXTENSIONEXECUTE *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_extensionexecute.md">D3DDDIARG_EXTENSIONEXECUTE</a> structure that describes the DirectX VA operation to perform.


## -returns



<i>ExtensionExecute</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The DirectX VA operation is successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>ExtensionExecute</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_extensionexecute.md">D3DDDIARG_EXTENSIONEXECUTE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_EXTENSIONEXECUTE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

