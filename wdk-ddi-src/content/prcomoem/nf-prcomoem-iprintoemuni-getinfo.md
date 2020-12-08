---
UID: NF:prcomoem.IPrintOemUni.GetInfo
title: IPrintOemUni::GetInfo (prcomoem.h)
description: A rendering plug-in's IPrintOemUni::GetInfo method returns identification information.
old-location: print\iprintoemuni_getinfo.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintOemUni::GetInfo"]
ms.keywords: GetInfo, GetInfo method [Print Devices], GetInfo method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],GetInfo method, IPrintOemUni.GetInfo, IPrintOemUni::GetInfo, prcomoem/IPrintOemUni::GetInfo, print.iprintoemuni_getinfo, print_unidrv-pscript_rendering_67919d6c-27a7-4f53-b558-9a6d6b391dad.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemUni::GetInfo
 - prcomoem/IPrintOemUni::GetInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintOemUni.GetInfo
---

# IPrintOemUni::GetInfo


## -description

A rendering plug-in's <code>IPrintOemUni::GetInfo</code> method returns identification information.

## -parameters

### -param dwMode

Contains one of the following caller-supplied integer constants.





#### OEMGI_GETREQUESTEDHELPERINTERFACES

The method must write the bit flag value of OEMPUBLISH_IPRINTCOREHELPER to the buffer <i>pBuffer</i> if the <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-publishdriverinterface">IPrintOemUni::PublishDriverInterface</a> method should be called with parameter <i>pIUnknown</i> pointing to an object that implements the <a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni">IPrintCoreHelperUni Interface</a>.





#### OEMGI_GETSIGNATURE

The method must return a unique four-byte identification signature. The plug-in must also place this signature in <a href="/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structures, as described in the description of the <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemcuipparam">OEMCUIPPARAM</a>. structure's <b>pOEMOptItems</b> member.





#### OEMGI_GETVERSION

The method must return the user interface plug-in's version number as a DWORD. The version format is developer-defined.

### -param pBuffer

Caller-supplied pointer to memory allocated to receive the information specified by <i>dwInfo</i>.

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
The operation failed.

</td>
</tr>
</table>

## -remarks

A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::GetInfo</code> method, which is called immediately after the plug-in is loaded. The method should return the specified information by writing it to the address specified by <i>pBuffer</i> and writing the size, in bytes, of the returned information into the location specified by <i>pcbNeeded</i>.

If <i>pBuffer</i> is <b>NULL</b>, the method should just use <i>pcbNeeded</i> to return the number of bytes required to store the specified information.

For more information about creating and installing rendering plug-ins, see <a href="/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-getinfo">IPrintOemPS::GetInfo</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-getinfo">IPrintOemUI::GetInfo</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemuni">IPrintOemUni</a>
