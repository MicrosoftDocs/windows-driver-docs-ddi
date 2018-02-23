---
UID: NF:wudfddi.IWDFNamedPropertyStore.GetNameCount
title: IWDFNamedPropertyStore::GetNameCount method
author: windows-driver-content
description: The GetNameCount method retrieves the number of properties in a property store.
old-location: wdf\iwdfnamedpropertystore_getnamecount.htm
old-project: wdf
ms.assetid: 9891e360-ca09-4ebb-8cf4-d08b3456910c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetNameCount method, GetNameCount, IWDFNamedPropertyStore, IWDFNamedPropertyStore interface, GetNameCount method, wdf.iwdfnamedpropertystore_getnamecount, umdf.iwdfnamedpropertystore_getnamecount, UMDFPropertyStoreObjectRef_94f4d4d8-43e9-4901-a2bb-613761069daf.xml, wudfddi/IWDFNamedPropertyStore::GetNameCount, GetNameCount method, IWDFNamedPropertyStore interface, IWDFNamedPropertyStore::GetNameCount
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFNamedPropertyStore.GetNameCount
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFNamedPropertyStore::GetNameCount method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNameCount</b> method retrieves the number of properties in a property store.


## -syntax


````
HRESULT GetNameCount(
  [out] DWORD *pdwCount
);
````


## -parameters




### -param pdwCount [out]

A pointer to a variable that receives the number of properties in the property store. 


## -returns



<b>GetNameCount</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFNamedPropertyStore::GetNameCount method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

