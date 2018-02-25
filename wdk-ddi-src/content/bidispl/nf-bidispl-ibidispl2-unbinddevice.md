---
UID: NF:bidispl.IBidiSpl2.UnbindDevice
title: IBidiSpl2::UnbindDevice method
author: windows-driver-content
description: The UnbindDevice method releases a printer from a bidirectional printer communication (bidi communication) request.
old-location: print\ibidispl2_ibidispl2__unbinddevice.htm
old-project: print
ms.assetid: 26f3fc82-051d-4827-8b59-ac2c99f4d2c5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 2, :, B, D, I, IBidiSpl2, IBidiSpl2 interface [Print Devices], UnbindDevice method, IBidiSpl2::UnbindDevice, S, U, UnbindDevice method [Print Devices], UnbindDevice method [Print Devices], IBidiSpl2 interface, UnbindDevice,IBidiSpl2.UnbindDevice, _win32_IBidiSpl2_UnbindDevice, b, bidispl/IBidiSpl2::UnbindDevice, c, d, e, gdi.ibidispl2_ibidispl2__unbinddevice, i, l, n, p, print.ibidispl2_ibidispl2__unbinddevice, v"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: bidispl.h
req.dll: Bidispl.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	bidispl.dll
apiname:
-	IBidiSpl2.UnbindDevice
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# IBidiSpl2::UnbindDevice method


## -description


The <b>UnbindDevice</b> method releases a printer from a bidirectional printer communication (bidi communication) request.


## -syntax


````
HRESULT UnbindDevice();
````


## -parameters






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

<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="..\bidispl\nn-bidispl-ibidispl2.md">IBidiSpl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiSpl2::UnbindDevice method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

