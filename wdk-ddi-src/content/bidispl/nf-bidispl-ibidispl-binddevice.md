---
UID: NF:bidispl.IBidiSpl.BindDevice
title: IBidiSpl::BindDevice
author: windows-driver-content
description: The BindDevice method binds a printer to a bidi request. This method is similar to the OpenPrinter function.
old-location: print\ibidispl_ibidispl__binddevice.htm
old-project: print
ms.assetid: 880ff314-c79d-4395-83ad-ce61bb8da5b5
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: BIDI_ACCESS_ADMINISTRATOR, BIDI_ACCESS_USER, BindDevice, BindDevice method [Print Devices], BindDevice method [Print Devices],IBidiSpl interface, IBidiSpl interface [Print Devices],BindDevice method, IBidiSpl.BindDevice, IBidiSpl::BindDevice, _win32_IBidiSpl_BindDevice, bidispl/IBidiSpl::BindDevice, gdi.ibidispl_ibidispl__binddevice, print.ibidispl_ibidispl__binddevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	bidispl.dll
api_name:
-	IBidiSpl.BindDevice
product: Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl::BindDevice


## -description


The <b>BindDevice</b> method binds a printer to a bidi request. This method is similar to the <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a> function.


## -parameters




### -param pszDeviceName [in]

A pointer to a null-terminated string that contains name of the printer or print server. If <b>NULL</b>, it indicates the local printer server.


### -param dwAccess [in]

The access privileges for the printer. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="BIDI_ACCESS_ADMINISTRATOR"></a><a id="bidi_access_administrator"></a><dl>
<dt><b>BIDI_ACCESS_ADMINISTRATOR</b></dt>
</dl>
</td>
<td width="60%">
Permits users to perform all administrative tasks and basic printing operations except for SYNCHRONIZE. This is the same as PRINTER_ALL_ACCESS in <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_ACCESS_USER"></a><a id="bidi_access_user"></a><dl>
<dt><b>BIDI_ACCESS_USER</b></dt>
</dl>
</td>
<td width="60%">
Permits users to perform basic printing operations. This is the same as PRINTER_ACCESS_USE in <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>.

</td>
</tr>
</table>
 


## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144980">IBidiSpl</a>



<a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>
 

 

