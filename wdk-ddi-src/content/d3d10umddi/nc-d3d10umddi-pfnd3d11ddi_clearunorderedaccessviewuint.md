---
UID: NC:d3d10umddi.PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT
title: PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT
author: windows-driver-content
description: The ClearUnorderedAccessViewUINT function clears the specified unordered-access view by setting it to a constant value.
old-location: display\clearunorderedaccessviewuint.htm
old-project: display
ms.assetid: 7cdc81a9-e468-4da8-bc32-9e9cea1fd60d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.clearunorderedaccessviewuint, ClearUnorderedAccessViewUINT callback function [Display Devices], ClearUnorderedAccessViewUINT, PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT, PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT, d3d10umddi/ClearUnorderedAccessViewUINT, UserModeDisplayDriverDx11_Functions_c31370b0-9955-4ccb-b540-92b15fc27cc5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: ClearUnorderedAccessViewUINT is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
apiname: 
-	ClearUnorderedAccessViewUINT
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT callback


## -description


The <b>ClearUnorderedAccessViewUINT</b> function clears the specified unordered-access view by setting it to a constant value. 


## -prototype


````
PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT ClearUnorderedAccessViewUINT;

VOID APIENTRY ClearUnorderedAccessViewUINT(
  _In_       D3D10DDI_HDEVICE              hDevice,
  _In_       D3D11DDI_HUNORDEREDACCESSVIEW hUnorderedAccessView,
  _In_ const UINT[4]                       pUints
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11DDI_HUNORDEREDACCESSVIEW



### -param UINT[4]






#### - pUints [in]

 A four-element array of unsigned integers that the driver uses to clear an unordered-access view. 


#### - hUnorderedAccessView [in]

 A handle to the unordered-access view to clear. 


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. 



## -remarks


The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>ClearUnorderedAccessViewUINT</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

