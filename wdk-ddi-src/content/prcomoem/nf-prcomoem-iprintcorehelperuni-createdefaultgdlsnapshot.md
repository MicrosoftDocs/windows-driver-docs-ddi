---
UID: NF:prcomoem.IPrintCoreHelperUni.CreateDefaultGDLSnapshot
title: IPrintCoreHelperUni::CreateDefaultGDLSnapshot
author: windows-driver-content
description: The IPrintCoreHelperUni::CreateDefaultGDLSnapshot method gets a GDL snapshot based on the driver default configuration.
old-location: print\iprintcorehelperuni_createdefaultgdlsnapshot.htm
old-project: print
ms.assetid: 987c3721-d8a8-4aac-8f42-6eac9b5ccdc5
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: CreateDefaultGDLSnapshot, CreateDefaultGDLSnapshot method [Print Devices], CreateDefaultGDLSnapshot method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],CreateDefaultGDLSnapshot method, IPrintCoreHelperUni.CreateDefaultGDLSnapshot, IPrintCoreHelperUni::CreateDefaultGDLSnapshot, prcomoem/IPrintCoreHelperUni::CreateDefaultGDLSnapshot, print.iprintcorehelperuni_createdefaultgdlsnapshot, print_unidrv-pscript_allplugins_8149f1a2-7974-47b9-a0fa-9981534abb06.xml
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
-	prcomoem.h
api_name:
-	IPrintCoreHelperUni.CreateDefaultGDLSnapshot
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperUni::CreateDefaultGDLSnapshot


## -description


The <code>IPrintCoreHelperUni::CreateDefaultGDLSnapshot</code> method gets a GDL snapshot based on the driver default configuration.


## -parameters




### -param dwFlags [in]

This parameter is reserved and must be set to zero.


### -param ppSnapshotStream [out]

A pointer to a stream that supplies the XML version of the GDL snapshot.


## -returns



<code>IPrintCoreHelperUni::CreateDefaultGDLSnapshot</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -see-also




<a href="https://msdn.microsoft.com/e581d190-8185-45c1-80c7-ff8eb305360e">IPrintCoreHelperUni</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552923">IPrintCoreHelperUni::CreateGDLSnapshot</a>
 

 

