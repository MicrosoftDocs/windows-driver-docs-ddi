---
UID: NF:prcomoem.IPrintCoreHelperUni.CreateDefaultGDLSnapshot
title: IPrintCoreHelperUni::CreateDefaultGDLSnapshot method
author: windows-driver-content
description: The IPrintCoreHelperUni::CreateDefaultGDLSnapshot method gets a GDL snapshot based on the driver default configuration.
old-location: print\iprintcorehelperuni_createdefaultgdlsnapshot.htm
old-project: print
ms.assetid: 987c3721-d8a8-4aac-8f42-6eac9b5ccdc5
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: CreateDefaultGDLSnapshot method [Print Devices], print_unidrv-pscript_allplugins_8149f1a2-7974-47b9-a0fa-9981534abb06.xml, print.iprintcorehelperuni_createdefaultgdlsnapshot, CreateDefaultGDLSnapshot method [Print Devices], IPrintCoreHelperUni interface, IPrintCoreHelperUni::CreateDefaultGDLSnapshot, IPrintCoreHelperUni interface [Print Devices], CreateDefaultGDLSnapshot method, prcomoem/IPrintCoreHelperUni::CreateDefaultGDLSnapshot, CreateDefaultGDLSnapshot, IPrintCoreHelperUni
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintCoreHelperUni.CreateDefaultGDLSnapshot
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintCoreHelperUni::CreateDefaultGDLSnapshot method


## -description


The <code>IPrintCoreHelperUni::CreateDefaultGDLSnapshot</code> method gets a GDL snapshot based on the driver default configuration.


## -syntax


````
HRESULT CreateDefaultGDLSnapshot(
  [in]  DWORD    dwFlags,
  [out] LPSTREAM *ppSnapshotStream
);
````


## -parameters




### -param dwFlags [in]

This parameter is reserved and must be set to zero.


### -param ppSnapshotStream [out]

A pointer to a stream that supplies the XML version of the GDL snapshot.


## -returns


<code>IPrintCoreHelperUni::CreateDefaultGDLSnapshot</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552923">IPrintCoreHelperUni::CreateGDLSnapshot</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperUni::CreateDefaultGDLSnapshot method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

