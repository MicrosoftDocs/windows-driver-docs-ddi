---
UID: NC:d3dumddi.PFND3DDDI_DESTROYCRYPTOSESSION
title: PFND3DDDI_DESTROYCRYPTOSESSION
author: windows-driver-content
description: The DestroyCryptoSession function releases resources for the encryption session that the CreateCryptoSession function creates.
old-location: display\destroycryptosession.htm
tech.root: display
ms.assetid: 4035ef73-e1a2-49e4-808d-c40c980393a4
ms.date: 5/10/2018
ms.keywords: DestroyCryptoSession, DestroyCryptoSession callback function [Display Devices], PFND3DDDI_DESTROYCRYPTOSESSION, PFND3DDDI_DESTROYCRYPTOSESSION callback, UserModeDisplayDriver_Functions_c1fa988d-a8b7-4538-94cd-d364873f4216.xml, d3dumddi/DestroyCryptoSession, display.destroycryptosession
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyCryptoSession is supported beginning with the Windows 7 operating system.
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	DestroyCryptoSession
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYCRYPTOSESSION callback function


## -description


The <b>DestroyCryptoSession</b> function releases resources for the encryption session that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function creates. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543028">D3DDDIARG_DESTROYCRYPTOSESSION</a> structure that contains one member that specifies the handle to the encryption session to destroy. 


## -returns



<b>DestroyCryptoSession</b> returns one of the following values:

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
The encryption session is successfully destroyed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451632">DestroyCryptoSession</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543028">D3DDDIARG_DESTROYCRYPTOSESSION</a>
 

 

