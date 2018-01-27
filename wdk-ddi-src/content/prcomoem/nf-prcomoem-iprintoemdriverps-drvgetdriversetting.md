---
UID: NF:prcomoem.IPrintOemDriverPS.DrvGetDriverSetting
title: IPrintOemDriverPS::DrvGetDriverSetting method
author: windows-driver-content
description: The IPrintOemDriverPS::DrvGetDriverSetting method is provided by the Pscript5 driver so that rendering plug-ins can obtain the current status of printer features and other internal information.
old-location: print\iprintoemdriverps_drvgetdriversetting.htm
old-project: print
ms.assetid: c3e9775b-a5ab-42e4-a889-a746a7243b37
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: prcomoem/IPrintOemDriverPS::DrvGetDriverSetting, IPrintOemDriverPS, DrvGetDriverSetting method [Print Devices], print_unidrv-pscript_rendering_eb83bce7-ee89-4a4b-a72d-214d2d8054ee.xml, print.iprintoemdriverps_drvgetdriversetting, DrvGetDriverSetting, IPrintOemDriverPS::DrvGetDriverSetting, DrvGetDriverSetting method [Print Devices], IPrintOemDriverPS interface, IPrintOemDriverPS interface [Print Devices], DrvGetDriverSetting method
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
-	IPrintOemDriverPS.DrvGetDriverSetting
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemDriverPS::DrvGetDriverSetting method


## -description


The <code>IPrintOemDriverPS::DrvGetDriverSetting</code> method is provided by the Pscript5 driver so that rendering plug-ins can obtain the current status of printer features and other internal information.


## -syntax


````
HRESULT DrvGetDriverSetting(
   PVOID  pdriverobj,
   PCSTR  Feature,
   PVOID  pOutput,
   DWORD  cbSize,
   PDWORD pcbNeeded,
   PDWORD pdwOptionsReturned
);
````


## -parameters




### -param pdriverobj

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param Feature

Caller supplied value identifying the printer feature for which option settings will be returned. This can be either a string pointer or a constant, as described in the following Remarks section.


### -param pOutput

Caller-supplied pointer to a buffer to receive the specified information.


### -param cbSize

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutput</i>.


### -param pcbNeeded

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.


### -param pdwOptionsReturned

Caller-supplied pointer to a location to receive the number of option strings placed in <i>pOutput</i>.


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
The operation failed

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


When the <code>IPrintOemDriverPS::DrvGetDriverSetting</code> method is called, either a string pointer or a constant value can be specified for <i>pFeatureKeyword</i>.
<ul>
<li>
If <i>pFeatureKeyword</i> is a string, it must represent a keyword argument to an *<b>OpenUI</b> entry in a Pscript5 minidriver's PPD file.

The method should return one or more NULL-terminated strings in the buffer pointed to by <i>pOutput</i>. Each string should represent the name of a currently selected option. The number of strings should be returned in <i>pdwOptionsReturned</i>.

</li>
<li>
If <i>pFeatureKeyword</i> is a constant, it must be one of the <b>OEMGDS_</b>-prefixed constants defined in printoem.h. The method should return the value indicated by the specified constant by placing it in the buffer pointed to by <i>pOutput</i>. The value returned in <i>pdwOptionsReturned</i> must be 1.

</li>
</ul>

