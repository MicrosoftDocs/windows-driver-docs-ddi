---
UID: NF:bidispl.IBidiSpl2.BindDevice
title: IBidiSpl2::BindDevice method
author: windows-driver-content
description: The IBidiSpl2::BindDevice method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the OpenPrinter function.
old-location: print\ibidispl2_ibidispl2__binddevice.htm
old-project: print
ms.assetid: c5bd238d-4b85-4463-aa73-ff3a7798ccff
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IBidiSpl2, IBidiSpl2::BindDevice, BindDevice
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
req.alt-api: IBidiSpl2.IBidiSpl2::BindDevice
req.alt-loc: bidispl.dll
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
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# IBidiSpl2::BindDevice method



## -description
The <b>IBidiSpl2::BindDevice</b> method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a> function.



## -syntax

````
HRESULT IBidiSpl2::BindDevice(
  [in] const LPCWSTR pszDeviceName,
  [in] const DWORD   dwAccess
);
````


## -parameters

### -param pszDeviceName [in]

A pointer to a null-terminated string that contains the name of the printer or print server. If <b>NULL</b>, this parameter indicates the local print server.


### -param dwAccess [in]

The access privileges for the printer. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param BIDI_ACCESS_ADMINISTRATOR

</td>
<td width="60%">
Permits users to perform all administrative tasks and basic printing operations except for SYNCHRONIZE. This is the same as PRINTER_ALL_ACCESS in <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>.

</td>
</tr>
<tr>

### -param BIDI_ACCESS_USER

</td>
<td width="60%">
Permits users to perform basic printing operations. This is the same as PRINTER_ACCESS_USE in <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>.

</td>
</tr>
</table>
 


## -returns
The method returns one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation was successful.
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>The interface handle is invalid.
<dl>
<dt><b>None of the above</b></dt>
</dl>The <b>HRESULT</b> contains an error code that corresponds to the last error.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\bidispl\nn-bidispl-ibidispl2.md">IBidiSpl2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiSpl2::IBidiSpl2::BindDevice method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

