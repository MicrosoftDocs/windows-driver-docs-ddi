---
UID: NF:wudfddi.IWDFNamedPropertyStore.GetNameAt
title: IWDFNamedPropertyStore::GetNameAt method
author: windows-driver-content
description: The GetNameAt method retrieves the name of a property.
old-location: wdf\iwdfnamedpropertystore_getnameat.htm
old-project: wdf
ms.assetid: f6ebf45b-b411-4684-b430-0b17a56ec0c0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: umdf.iwdfnamedpropertystore_getnameat, wudfddi/IWDFNamedPropertyStore::GetNameAt, IWDFNamedPropertyStore::GetNameAt, UMDFPropertyStoreObjectRef_d7568b53-9673-4344-bbbc-100fc19aaba5.xml, GetNameAt method, IWDFNamedPropertyStore, GetNameAt, IWDFNamedPropertyStore interface, GetNameAt method, GetNameAt method, IWDFNamedPropertyStore interface, wdf.iwdfnamedpropertystore_getnameat
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
-	IWDFNamedPropertyStore.GetNameAt
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFNamedPropertyStore::GetNameAt method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNameAt</b> method retrieves the name of a property.


## -syntax


````
HRESULT GetNameAt(
  [in]  DWORD iProp,
  [out] PWSTR *ppwszName
);
````


## -parameters




### -param iProp [in]

The zero-based index of the property that <b>GetNameAt</b> retrieves the name from.


### -param ppwszName [out]

A pointer to a variable that receives a pointer to a <b>NULL</b>-terminated string that contains the name of the property. 


## -returns


<b>GetNameAt</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.



## -remarks


For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFNamedPropertyStore::GetNameAt method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

