---
UID: NF:prcomoem.IPrintCoreHelperUni.CreateGDLSnapshot
title: IPrintCoreHelperUni::CreateGDLSnapshot (prcomoem.h)
description: The IPrintCoreHelperUni::CreateGDLSnapshot method creates a GDL snapshot of the driver configuration file based on the current configuration.
old-location: print\iprintcorehelperuni_creategdlsnapshot.htm
tech.root: print
ms.assetid: 3dd9c7f9-27d4-45d2-8692-4270818c1823
ms.date: 04/20/2018
ms.keywords: CreateGDLSnapshot, CreateGDLSnapshot method [Print Devices], CreateGDLSnapshot method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],CreateGDLSnapshot method, IPrintCoreHelperUni.CreateGDLSnapshot, IPrintCoreHelperUni::CreateGDLSnapshot, prcomoem/IPrintCoreHelperUni::CreateGDLSnapshot, print.iprintcorehelperuni_creategdlsnapshot, print_unidrv-pscript_allplugins_c45d077d-295f-4636-829f-8595d43cd5ed.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelperUni.CreateGDLSnapshot"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintCoreHelperUni.CreateGDLSnapshot
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperUni::CreateGDLSnapshot


## -description


The <code>IPrintCoreHelperUni::CreateGDLSnapshot</code> method creates a GDL snapshot of the driver configuration file based on the current configuration. 


## -parameters




### -param pDevmode [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure. If this pointer is provided, <code>IPrintCoreHelperUni::CreateGDLSnapshot</code>  should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider, there is no default DEVMODEW structure and the <i>pDevmode</i> parameter is required.


### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter. 


### -param dwFlags [in]

Reserved for system use. This parameter must be set to zero.


### -param ppSnapshotStream [out]

A pointer to a stream that supplies the XML version of the GDL snapshot.


## -returns



<code>IPrintCoreHelperUni::CreateGDLSnapshot</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni">IPrintCoreHelperUni</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-createdefaultgdlsnapshot">IPrintCoreHelperUni::CreateDefaultGDLSnapshot</a>
 

 

