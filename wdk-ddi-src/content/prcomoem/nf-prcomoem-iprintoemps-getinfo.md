---
UID: NF:prcomoem.IPrintOemPS.GetInfo
title: IPrintOemPS::GetInfo
author: windows-driver-content
description: A rendering plug-in's IPrintOemPS::GetInfo method returns identification information.
old-location: print\iprintoemps_getinfo.htm
old-project: print
ms.assetid: 9a8b060d-675b-4171-b75e-6df55cd0667f
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: GetInfo, GetInfo method [Print Devices], GetInfo method [Print Devices],IPrintOemPS interface, IPrintOemPS interface [Print Devices],GetInfo method, IPrintOemPS.GetInfo, IPrintOemPS::GetInfo, prcomoem/IPrintOemPS::GetInfo, print.iprintoemps_getinfo, print_unidrv-pscript_rendering_1312f0cf-aa7d-45df-8e77-eed5dedd2f10.xml
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
-	Prcomoem.h
api_name:
-	IPrintOemPS.GetInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPS::GetInfo


## -description


A rendering plug-in's <code>IPrintOemPS::GetInfo</code> method returns identification information.


## -parameters




### -param dwMode

Contains one of the following caller-supplied integer constants.





#### OEMGI_GETPUBLISHERINFO

The method must indicate whether the rendering plug-in will be using "publishing mode". The <i>pBuffer</i> parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561851">PUBLISHERINFO</a> structure, to be filled in by the method. For more information, see the following Remarks section.





#### OEMGI_GETREQUESTEDHELPERINTERFACES

The method must write the bit flag value of OEMPUBLISH_IPRINTCOREHELPER to the buffer <i>pBuffer</i> if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553228">IPrintOemPS::PublishDriverInterface</a> method should be called with parameter <i>pIUnknown</i> pointing to an object that implements the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552906">IPrintCoreHelperPS Interface</a>.





#### OEMGI_GETSIGNATURE

The method must return a unique four-byte identification signature. The plug-in must also place this signature in <a href="https://msdn.microsoft.com/library/windows/hardware/ff559656">OPTITEM</a> structures, as described in the description of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557653">OEMCUIPPARAM</a>. structure's <b>pOEMOptItems</b> member.





#### OEMGI_GETVERSION

The method must return the user interface plug-in's version number as a DWORD. The version format is developer-defined.


### -param pBuffer

Caller-supplied pointer to memory allocated to receive the information specified by <i>dwMode</i>.


### -param cbSize

Caller-supplied size of the buffer pointed to by <i>pBuffer</i>.


### -param pcbNeeded

Caller-supplied pointer to a location to receive the number of bytes written into the buffer pointed to by <i>pBuffer</i>.


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



Rendering plug-ins for Pscript5 are required to implement the <code>IPrintOemPS::GetInfo</code> method, which is called immediately after the plug-in is loaded. The method should return the specified information by writing it to the address specified by <i>pBuffer</i> and writing the size, in bytes, of the returned information into the location specified by <i>pcbNeeded</i>.

If <i>pBuffer</i> is <b>NULL</b>, the method should just use <i>pcbNeeded</i> to return the number of bytes required to store the specified information.

In "publishing mode", all font information to be downloaded is placed in the job header. Each font is downloaded only once and can be used for any page, allowing the job to be page-order independent. If <i>dwMode</i> is OEMGI_GETPUBLISHERINFO but the plug-in does not support publishing mode, <code>IPrintOemPS::GetInfo</code> should return E_NOTIMPL.

For more information about creating and installing rendering plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/14c545b7-8080-424f-9164-f97ef8a1acc2">IPrintOemPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554178">IPrintOemUI::GetInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554256">IPrintOemUni::GetInfo</a>
 

 

