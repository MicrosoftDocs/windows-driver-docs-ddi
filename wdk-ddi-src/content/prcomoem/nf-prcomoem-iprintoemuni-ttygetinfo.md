---
UID: NF:prcomoem.IPrintOemUni.TTYGetInfo
title: IPrintOemUni::TTYGetInfo method
author: windows-driver-content
description: The IPrintOemUni::TTYGetInfo method enables a rendering plug-in to supply Unidrv with information relevant to text-only printers.
old-location: print\iprintoemuni_ttygetinfo.htm
old-project: print
ms.assetid: 0df8c555-4298-47e7-a6a7-43f101620e04
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: TTYGetInfo method [Print Devices], IPrintOemUni, print_unidrv-pscript_rendering_d98708b3-8e01-4037-a545-aee0e32a46c6.xml, print.iprintoemuni_ttygetinfo, IPrintOemUni interface [Print Devices], TTYGetInfo method, TTYGetInfo, TTYGetInfo method [Print Devices], IPrintOemUni interface, IPrintOemUni::TTYGetInfo, prcomoem/IPrintOemUni::TTYGetInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemUni.TTYGetInfo
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni::TTYGetInfo method


## -description


The <code>IPrintOemUni::TTYGetInfo</code> method enables a rendering plug-in to supply Unidrv with information relevant to text-only printers.


## -syntax


````
HRESULT TTYGetInfo(
   PDEVOBJ pdevobj,
   DWORD   dwInfoIndex,
   PVOID   pOutputBuf,
   DWORD   dwSize,
   DWORD   *pcbcNeeded
);
````


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param dwInfoIndex

Caller-supplied constant identifying the type of information being requested. The following constant values are defined:





#### OEMTTY_INFO_CODEPAGE

The <i>pOutputBuf</i> parameter points to a DWORD in which the method should return the number of the code page to be used.





#### OEMTTY_INFO_MARGINS

The <i>pOutputBuf</i> parameter points to a RECT structure in which the method should return page margin widths, in tenths of millimeters (for example, 20 represents 2 mm). If the entire page is printable, all margin values must be 0.





#### OEMTTY_INFO_NUM_UFMS

The <i>pOutputBuf</i> parameter points to a DWORD in which the method should return the number of resource IDs of the <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">UFMs</a> for 10, 12, and 17 CPI fonts. To actually obtain these resource IDs, perform a query using OEMTTY_INFO_UFM_IDS.





#### OEMTTY_INFO_UFM_IDS

The <i>pOutputBuf</i> parameter points to an array of DWORDs of sufficient size to hold the number of resource IDs of the UFMs for 10, 12, and 17 CPI fonts. (This number is obtained by using OEMTTY_INFO_NUM_UFMS in a query.) The method should return the resource IDs of the <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">UFMs</a> for 10,12, and 17 CPI fonts. 


### -param pOutputBuf

Caller-supplied pointer to a buffer to receive the requested information.


### -param dwSize

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutputBuf</i>.


### -param pcbcNeeded

Caller-supplied pointer to a location to receive the number of bytes written into the buffer pointed to by <i>pOutputBuf</i>. If the number of bytes required is smaller than the number specified by <i>dwSize</i>, the method should supply the required size and return E_FAIL.


## -returns



The method must return one of the following values.

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
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



The <code>IPrintOemUni::TTYGetInfo</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "TTYGetInfo" as input.



