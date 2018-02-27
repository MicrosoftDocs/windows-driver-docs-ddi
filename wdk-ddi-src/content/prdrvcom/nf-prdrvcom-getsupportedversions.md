---
UID: NF:prdrvcom.GetSupportedVersions
title: GetSupportedVersions function
author: windows-driver-content
description: The GetSupportedVersions function queries for the Direct3D interface versions that the driver supports.
old-location: display\getsupportedversions.htm
old-project: display
ms.assetid: b38683f3-42f2-4f5e-9482-f72e9f2e0a34
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: GetSupportedVersions, GetSupportedVersions callback function [Display Devices], PFND3D10_2DDI_GETSUPPORTEDVERSIONS, UserModeDisplayDriverDx11_Functions_065e47e6-c02d-4091-b614-a93aa834cbfb.xml, d3d10umddi/GetSupportedVersions, display.getsupportedversions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prdrvcom.h
req.include-header: D3d10umddi.h, Prdrvcom.h
req.target-type: Desktop
req.target-min-winverclnt: GetSupportedVersions is supported beginning with the Windows 7 operating system.
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
req.lib: NtosKrnl.exe
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
-	GetSupportedVersions
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# GetSupportedVersions function


## -description


The <i>GetSupportedVersions</i> function queries for the Direct3D interface versions that the driver supports. 


## -syntax


````
PFND3D10_2DDI_GETSUPPORTEDVERSIONS GetSupportedVersions;

HRESULT APIENTRY GetSupportedVersions(
  _In_      D3D10DDI_HADAPTER hAdapter,
  _Inout_   UINT32            *puEntries,
  _Out_opt_ UINT64            *pSupportedDDIInterfaceVersions
)
{ ... }
````


## -parameters




### -param hPrinter

TBD


### -param ppVersions

TBD


### -param cVersions

TBD




#### - hAdapter [in]

 A handle that identifies the graphics adapter. 


#### - pSupportedDDIInterfaceVersions [out, optional]

 A pointer to a block of memory that receives the array of Direct3D interface versions that the driver supports.


#### - puEntries [in, out]

A pointer to a variable that, on input, contains the number of entries that the <i>pSupportedDDIInterfaceVersions</i> array should return and, on output, the number of entries that the <i>pSupportedDDIInterfaceVersions</i> array actually returns. 


## -returns



<i>GetSupportedVersions</i> returns one of the following values:

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
The capabilities are successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetSupportedVersions</i> could not allocate memory that is required for it to complete.

</td>
</tr>
</table>
 




## -remarks



When the Direct3D runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10_2</a> function, the <b>Interface</b> and <b>Version</b> members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a> structure contain the DDI version that the runtime uses to instantiate the driver. The driver can completely ignore these members. The driver can instead return capabilities and version information out through its <i>GetSupportedVersions</i> function. 




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddi_adapterfuncs.md">D3D10_2DDI_ADAPTERFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10_2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_2DDI_GETSUPPORTEDVERSIONS callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

