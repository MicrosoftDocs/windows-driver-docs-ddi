---
UID: NC:d3dumddi.PFND3DDDI_GETQUERYDATA
title: PFND3DDDI_GETQUERYDATA
author: windows-driver-content
description: The GetQueryData function retrieves information about a query.
old-location: display\getquerydata.htm
old-project: display
ms.assetid: 64daec14-8e16-4df3-bb0c-27760223b86c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: GetQueryData, GetQueryData callback function [Display Devices], PFND3DDDI_GETQUERYDATA, UserModeDisplayDriver_Functions_05870f6b-5971-4201-9910-c8c8c548878a.xml, d3dumddi/GetQueryData, display.getquerydata
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
-	GetQueryData
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_GETQUERYDATA callback


## -description


The <i>GetQueryData</i> function retrieves information about a query.


## -prototype


````
PFND3DDDI_GETQUERYDATA GetQueryData;

__checkReturn HRESULT APIENTRY GetQueryData(
  _In_          HANDLE                 hDevice,
  _Inout_ const D3DDDIARG_GETQUERYDATA *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getquerydata.md">D3DDDIARG_GETQUERYDATA</a> structure that contains the information about the query that is retrieved from the driver.


## -returns



<i>GetQueryData</i> returns one of the following values:

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
The query operation completed and the query result is available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
<i>GetQueryData</i> returned successfully. However, the query operation did not complete, so the query result is not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetQueryData</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The Microsoft Direct3D runtime can call <i>GetQueryData</i> at any time after calling the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_issuequery.md">IssueQuery</a> function. The user-mode display driver should check the current fence value against the value that is stored in the driver's private query structure to determine if the query issue is complete.

If the query is completed, the driver should return S_OK; otherwise, the driver should return S_FALSE. 

If a driver supports <a href="https://msdn.microsoft.com/906d6b31-a447-4a94-b1a5-cd3028722db7">runtime-handled multiple-processor optimizations</a> and exposes a DDI version of 0x0000000B or greater, the runtime will call <i>GetQueryData</i> in a reentrant manner. The driver returns the DDI-version value in the <b>DriverVersion</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a> function. When the runtime calls <i>GetQueryData</i> in a reentrant manner, one thread can execute inside <i>GetQueryData</i> while another thread that references the same display device executes inside of another user-mode display driver function. 




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_issuequery.md">IssueQuery</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getquerydata.md">D3DDDIARG_GETQUERYDATA</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETQUERYDATA callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

