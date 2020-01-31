---
UID: NF:bidispl.IBidiSpl2.UnbindDevice
title: IBidiSpl2::UnbindDevice (bidispl.h)
description: The UnbindDevice method releases a printer from a bidirectional printer communication (bidi communication) request.
old-location: print\ibidispl2_ibidispl2__unbinddevice.htm
tech.root: print
ms.assetid: 26f3fc82-051d-4827-8b59-ac2c99f4d2c5
ms.date: 04/20/2018
ms.keywords: IBidiSpl2 interface [Print Devices],UnbindDevice method, IBidiSpl2.UnbindDevice, IBidiSpl2::UnbindDevice, UnbindDevice, UnbindDevice method [Print Devices], UnbindDevice method [Print Devices],IBidiSpl2 interface, _win32_IBidiSpl2_UnbindDevice, bidispl/IBidiSpl2::UnbindDevice, gdi.ibidispl2_ibidispl2__unbinddevice, print.ibidispl2_ibidispl2__unbinddevice
f1_keywords:
 - "bidispl/IBidiSpl2.UnbindDevice"
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
- IBidiSpl2.UnbindDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl2::UnbindDevice


## -description


The <b>UnbindDevice</b> method releases a printer from a bidirectional printer communication (bidi communication) request.


## -returns



The method returns one of the following values.

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
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code that corresponds to the last error.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl2">IBidiSpl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/print-spooler-components">Print Spooler Components</a>
 

 

