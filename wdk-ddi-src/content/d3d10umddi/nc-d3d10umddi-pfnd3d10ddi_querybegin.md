---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYBEGIN
title: PFND3D10DDI_QUERYBEGIN
author: windows-driver-content
description: The QueryBegin function marks the beginning of a sequence of graphics commands for a query and transitions the query to the &#0034;building&#0034; state.
old-location: display\querybegin.htm
old-project: display
ms.assetid: 2f0a7462-83a6-47df-b5f6-b3706b875349
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.querybegin, QueryBegin callback function [Display Devices], QueryBegin, PFND3D10DDI_QUERYBEGIN, PFND3D10DDI_QUERYBEGIN, d3d10umddi/QueryBegin, UserModeDisplayDriverDx10_Functions_d456daf9-09b9-4174-8eba-7591ec45cd20.xml
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
-	QueryBegin
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D10DDI_QUERYBEGIN callback


## -description


The <i>QueryBegin</i> function marks the beginning of a sequence of graphics commands for a query and transitions the query to the "building" state. 


## -prototype


````
PFND3D10DDI_QUERYBEGIN QueryBegin;

VOID APIENTRY QueryBegin(
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

 A handle to the query object to begin.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver is not required to support the <i>QueryBegin</i> function for a D3D10DDI_QUERY_EVENT or D3D10DDI_QUERY_TIMESTAMP query operation. Such a query operation has an implied beginning. 

The Microsoft Direct3D runtime cannot call <i>QueryBegin</i> on a predicate that is currently bound to the pipeline through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a> function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>QueryBegin</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_QUERYBEGIN callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

