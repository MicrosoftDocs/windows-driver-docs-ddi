---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP
title: PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP
author: windows-driver-content
description: The DefaultConstantBufferUpdateSubresourceUP function updates a destination subresource region that stores constant buffers from a source system-memory region.
old-location: display\defaultconstantbufferupdatesubresourceup.htm
old-project: display
ms.assetid: 80086f1a-75f8-464f-973e-9c1e67725933
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.defaultconstantbufferupdatesubresourceup, DefaultConstantBufferUpdateSubresourceUP callback function [Display Devices], DefaultConstantBufferUpdateSubresourceUP, PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP, PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP, d3d10umddi/DefaultConstantBufferUpdateSubresourceUP, UserModeDisplayDriverDx10_Functions_1868c778-0475-4113-8b24-caf7f9822775.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
apiname:
-	DefaultConstantBufferUpdateSubresourceUP
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP callback


## -description


The <i>DefaultConstantBufferUpdateSubresourceUP</i> function updates a destination subresource region that stores constant buffers from a source system-memory region.


## -prototype


````
PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP DefaultConstantBufferUpdateSubresourceUP;

VOID APIENTRY DefaultConstantBufferUpdateSubresourceUP(
  _In_           D3D10DDI_HDEVICE   hDevice,
  _In_           D3D10DDI_HRESOURCE hDstResource,
  _In_           UINT               DstSubresource,
  _In_opt_ const D3D10_DDI_BOX      *pDstBox,
  _In_     const VOID               *pSysMemUP,
  _In_           UINT               RowPitch,
  _In_           UINT               DepthPitch
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HRESOURCE


### -param UINT








### -param *


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hDstResource [in]

 A handle to the destination resource to copy to.


#### - DstSubresource [in]

 An index that indicates the destination subresource to copy to. 


#### - pDstBox [in, optional]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_box.md">D3D10_DDI_BOX</a> structure that specifies the region of the destination subresource to copy data to. If <b>pDstBox</b> is <b>NULL</b>, the driver should copy to the entire destination subresouce. 


#### - pSysMemUP [in]

 A pointer to the beginning address of the source data that <i>DefaultConstantBufferUpdateSubresourceUP</i> uses to update the destination subresouce. 


#### - RowPitch [in]

 The offset, in bytes, to move to the next row of source data. 


#### - DepthPitch [in]

 The offset, in bytes, to move to the next depth slice of source data.


## -returns



None.

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



For more information about <i>DefaultConstantBufferUpdateSubresourceUP</i>, see the Remarks section of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a> function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>DefaultConstantBufferUpdateSubresourceUP</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_box.md">D3D10_DDI_BOX</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

