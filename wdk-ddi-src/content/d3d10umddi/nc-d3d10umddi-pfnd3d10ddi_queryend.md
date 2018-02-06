---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYEND
title: PFND3D10DDI_QUERYEND
author: windows-driver-content
description: The QueryEnd function marks the end of a sequence of graphics commands for a query and transitions the query to the &#0034;issued&#0034; state.
old-location: display\queryend.htm
old-project: display
ms.assetid: 5a231d7e-7e47-40ad-99d1-82661dec41d0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.queryend, QueryEnd callback function [Display Devices], QueryEnd, PFND3D10DDI_QUERYEND, PFND3D10DDI_QUERYEND, d3d10umddi/QueryEnd, UserModeDisplayDriverDx10_Functions_9897bbe4-a58c-430b-815a-eb4360ce8043.xml
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
-	QueryEnd
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_QUERYEND callback


## -description


The <i>QueryEnd</i> function marks the end of a sequence of graphics commands for a query and transitions the query to the "issued" state. 


## -prototype


````
PFND3D10DDI_QUERYEND QueryEnd;

VOID APIENTRY QueryEnd(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ D3D10DDI_HQUERY  hQuery
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D10DDI_HQUERY






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hQuery [in]

 A handle to the query object to end.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


If the driver supports the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querybegin.md">QueryBegin</a> function for a query operation, and if the Microsoft Direct3D runtime calls <i>QueryEnd</i> without call <i>QueryBegin</i>, the call is equivalent to first calling <i>QueryBegin</i> and then calling <i>QueryEnd</i> immediately afterward. In addition, the runtime cannot call <i>QueryEnd</i> on a predicate that is currently bound to the pipeline through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a> function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>QueryEnd</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querybegin.md">QueryBegin</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_QUERYEND callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

