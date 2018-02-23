---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWINDEXEDINSTANCED
title: PFND3D10DDI_DRAWINDEXEDINSTANCED
author: windows-driver-content
description: The DrawIndexedInstanced function draws particular instances of indexed primitives.
old-location: display\drawindexedinstanced.htm
old-project: display
ms.assetid: 3dc64562-9dc0-4d43-835d-6fdd509435f8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.drawindexedinstanced, DrawIndexedInstanced callback function [Display Devices], DrawIndexedInstanced, PFND3D10DDI_DRAWINDEXEDINSTANCED, PFND3D10DDI_DRAWINDEXEDINSTANCED, d3d10umddi/DrawIndexedInstanced, UserModeDisplayDriverDx10_Functions_7452fd0b-4fff-4321-b0ce-464ac0ad2f6d.xml
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
-	DrawIndexedInstanced
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_DRAWINDEXEDINSTANCED callback


## -description


The <b>DrawIndexedInstanced</b> function draws particular instances of indexed primitives.


## -prototype


````
PFND3D10DDI_DRAWINDEXEDINSTANCED DrawIndexedInstanced;

VOID APIENTRY DrawIndexedInstanced(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ UINT             IndexCountPerInstance,
  _In_ UINT             InstanceCount,
  _In_ UINT             StartIndexLocation,
  _In_ INT              BaseVertexLocation,
  _In_ UINT             StartInstanceLocation
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param UINT








### -param INT


#### - hDevice [in]

A handle to the display device (graphics context).


#### - IndexCountPerInstance [in]

The number of indexes per instance of the index buffer that indexes are read from to draw the primitives. 


#### - InstanceCount [in]

The number of instances of the index buffer that indexes are read from to draw the primitives. 


#### - StartIndexLocation [in]

The first index in the index buffer that indexes are read from to draw the primitives. 


#### - BaseVertexLocation [in]

The number that should be added to each index that is referenced by the various primitives to determine the actual index of the vertex elements in each vertex stream.


#### - StartInstanceLocation [in]

The first instance of the index buffer that indexes are read from to draw the primitives. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. 






## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>DrawIndexedInstanced</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_DRAWINDEXEDINSTANCED callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

