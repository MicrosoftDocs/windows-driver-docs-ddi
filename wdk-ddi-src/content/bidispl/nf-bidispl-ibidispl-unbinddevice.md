---
UID: NF:bidispl.IBidiSpl.UnbindDevice
title: IBidiSpl::UnbindDevice (bidispl.h)
description: The UnbindDevice method unbinds a printer from a bidi request.
old-location: print\ibidispl_ibidispl__unbinddevice.htm
tech.root: print
ms.assetid: 4c294d1d-5a37-4ea4-b50f-447260e885b1
ms.date: 04/20/2018
ms.keywords: IBidiSpl interface [Print Devices],UnbindDevice method, IBidiSpl.UnbindDevice, IBidiSpl::UnbindDevice, UnbindDevice, UnbindDevice method [Print Devices], UnbindDevice method [Print Devices],IBidiSpl interface, _win32_IBidiSpl_UnbindDevice, bidispl/IBidiSpl::UnbindDevice, gdi.ibidispl_ibidispl__unbinddevice, print.ibidispl_ibidispl__unbinddevice
ms.topic: method
f1_keywords:
 - "bidispl/IBidiSpl.UnbindDevice"
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
req.dll: Bidispl.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- bidispl.dll
api_name:
- IBidiSpl.UnbindDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl::UnbindDevice


## -description


The <b>UnbindDevice</b> method unbinds a printer from a bidi request.


## -parameters






## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Error Handling</a>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation was successfully carried out.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code corresponding to the last error.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nn-bidispl-ibidispl">IBidiSpl</a>
 

 

