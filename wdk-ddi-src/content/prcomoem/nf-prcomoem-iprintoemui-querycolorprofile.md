---
UID: NF:prcomoem.IPrintOemUI.QueryColorProfile
title: IPrintOemUI::QueryColorProfile
author: windows-driver-content
description: The IPrintOemUI::QueryColorProfile method allows a user interface plug-in to specify an ICC profile to use for color management.
old-location: print\iprintoemui_querycolorprofile.htm
old-project: print
ms.assetid: ce1131f9-4b9c-4f20-afc9-514ccbc7ecf7
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintOemUI interface [Print Devices],QueryColorProfile method, IPrintOemUI.QueryColorProfile, IPrintOemUI::QueryColorProfile, QueryColorProfile, QueryColorProfile method [Print Devices], QueryColorProfile method [Print Devices],IPrintOemUI interface, prcomoem/IPrintOemUI::QueryColorProfile, print.iprintoemui_querycolorprofile, print_unidrv-pscript_ui_7541a49f-f14c-4c73-88d7-80f316ae3602.xml
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUI.QueryColorProfile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI::QueryColorProfile


## -description


The <code>IPrintOemUI::QueryColorProfile</code> method allows a user interface plug-in to specify an ICC profile to use for color management.


## -parameters




### -param hPrinter

Caller-supplied printer handle.


### -param poemuiobj

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559571">OEMUIOBJ</a> structure.


### -param pPublicDM

Caller-supplied pointer to a validated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


### -param pOEMDM

Caller-supplied pointer to the user interface plug-in's private DEVMODEW structure members.


### -param ulQueryMode

One of the following caller-supplied bit flags, indicating the type of profile to be specified.

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
QCP_DEVICEPROFILE

</td>
<td>
The caller is requesting a device profile.

</td>
</tr>
<tr>
<td>
QCP_SOURCEPROFILE

</td>
<td>
The caller is requesting a source profile.

</td>
</tr>
</table>
 


### -param pvProfileData

Caller-supplied pointer to a buffer to receive profile information.


### -param pcbProfileData

Caller-supplied pointer to a value representing the size, in bytes, of the buffer pointed to by <i>pvProfileData</i>.


### -param pflProfileData

One of the following method-supplied bit flags, indicating the type of information the method is returning.

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
QCP_PROFILEDISK

</td>
<td>
The method is returning the file name of an ICC profile in the buffer pointed to by <i>pvProfileData</i>.

</td>
</tr>
<tr>
<td>
QCP_PROFILEMEMORY

</td>
<td>
The method is returning profile data in the buffer pointed to by <i>pvProfileData</i>.

</td>
</tr>
</table>
 


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



A user interface plug-in's <code>IPrintOemUI::QueryColorProfile</code> method performs the same types of operations as the <b>DrvQueryColorProfile</b> function that is exported by user-mode printer interface DLLs. For information about printer events and how they should be processed, see the description of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548573">DrvQueryColorProfile</a> function.

If you provide a user interface plug-in, the printer driver's <b>DrvQueryColorProfile</b> function calls the <code>IPrintOemUI::QueryColorProfile</code> method. The <b>DrvQueryColorProfile</b> function performs its own processing for the specified event, and then calls the <code>IPrintOemUI::QueryColorProfile</code> method to handle additional processing of the event.

If <code>IPrintOemUI::QueryColorProfile</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information about creating and installing user interface plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.



