---
UID: NF:bidispl.IBidiSpl.BindDevice
title: IBidiSpl::BindDevice (bidispl.h)
description: The BindDevice method binds a printer to a bidi request. This method is similar to the OpenPrinter function.
old-location: print\ibidispl_ibidispl__binddevice.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IBidiSpl::BindDevice"]
ms.keywords: BIDI_ACCESS_ADMINISTRATOR, BIDI_ACCESS_USER, BindDevice, BindDevice method [Print Devices], BindDevice method [Print Devices],IBidiSpl interface, IBidiSpl interface [Print Devices],BindDevice method, IBidiSpl.BindDevice, IBidiSpl::BindDevice, _win32_IBidiSpl_BindDevice, bidispl/IBidiSpl::BindDevice, gdi.ibidispl_ibidispl__binddevice, print.ibidispl_ibidispl__binddevice
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IBidiSpl::BindDevice
 - bidispl/IBidiSpl::BindDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl.BindDevice
---

# IBidiSpl::BindDevice


## -description

The <b>BindDevice</b> method binds a printer to a bidi request. This method is similar to the <a href="/windows-hardware/drivers/print/openprinter">OpenPrinter</a> function.

## -parameters

### -param pszDeviceName 

[in]
A pointer to a null-terminated string that contains name of the printer or print server. If <b>NULL</b>, it indicates the local printer server.

### -param dwAccess 

[in]
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
Permits users to perform all administrative tasks and basic printing operations except for SYNCHRONIZE. This is the same as PRINTER_ALL_ACCESS in <a href="/windows-hardware/drivers/print/openprinter">OpenPrinter</a>.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_ACCESS_USER"></a><a id="bidi_access_user"></a><dl>
<dt><b>BIDI_ACCESS_USER</b></dt>
</dl>
</td>
<td width="60%">
Permits users to perform basic printing operations. This is the same as PRINTER_ACCESS_USE in <a href="/windows-hardware/drivers/print/openprinter">OpenPrinter</a>.

</td>
</tr>
</table>

## -returns

The method returns one of the following values. For more information about COM error codes, see <a href="/windows/win32/com/com-error-codes">COM Error Codes</a>.

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

<a href="/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl">IBidiSpl</a>



<a href="/windows-hardware/drivers/print/openprinter">OpenPrinter</a>
