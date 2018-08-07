---
UID: NF:wudfddi.IWDFNamedPropertyStore.GetNameCount
title: IWDFNamedPropertyStore::GetNameCount
author: windows-driver-content
description: The GetNameCount method retrieves the number of properties in a property store.
old-location: wdf\iwdfnamedpropertystore_getnamecount.htm
tech.root: wdf
ms.assetid: 9891e360-ca09-4ebb-8cf4-d08b3456910c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetNameCount, GetNameCount method, GetNameCount method,IWDFNamedPropertyStore interface, IWDFNamedPropertyStore interface,GetNameCount method, IWDFNamedPropertyStore.GetNameCount, IWDFNamedPropertyStore::GetNameCount, UMDFPropertyStoreObjectRef_94f4d4d8-43e9-4901-a2bb-613761069daf.xml, umdf.iwdfnamedpropertystore_getnamecount, wdf.iwdfnamedpropertystore_getnamecount, wudfddi/IWDFNamedPropertyStore::GetNameCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFNamedPropertyStore.GetNameCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFNamedPropertyStore::GetNameCount


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNameCount</b> method retrieves the number of properties in a property store.


## -parameters




### -param pdwCount [out]

A pointer to a variable that receives the number of properties in the property store. 


## -returns



<b>GetNameCount</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560164">IWDFNamedPropertyStore</a>
 

 

