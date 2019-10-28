---
UID: NF:wudfddi.IWDFNamedPropertyStore.GetNameAt
title: IWDFNamedPropertyStore::GetNameAt (wudfddi.h)
description: The GetNameAt method retrieves the name of a property.
old-location: wdf\iwdfnamedpropertystore_getnameat.htm
tech.root: wdf
ms.assetid: f6ebf45b-b411-4684-b430-0b17a56ec0c0
ms.date: 02/26/2018
ms.keywords: GetNameAt, GetNameAt method, GetNameAt method,IWDFNamedPropertyStore interface, IWDFNamedPropertyStore interface,GetNameAt method, IWDFNamedPropertyStore.GetNameAt, IWDFNamedPropertyStore::GetNameAt, UMDFPropertyStoreObjectRef_d7568b53-9673-4344-bbbc-100fc19aaba5.xml, umdf.iwdfnamedpropertystore_getnameat, wdf.iwdfnamedpropertystore_getnameat, wudfddi/IWDFNamedPropertyStore::GetNameAt
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFNamedPropertyStore.GetNameAt"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFNamedPropertyStore.GetNameAt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFNamedPropertyStore::GetNameAt


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNameAt</b> method retrieves the name of a property.


## -parameters




### -param iProp [in]

The zero-based index of the property that <b>GetNameAt</b> retrieves the name from.


### -param ppwszName [out]

A pointer to a variable that receives a pointer to a <b>NULL</b>-terminated string that contains the name of the property. 


## -returns



<b>GetNameAt</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfnamedpropertystore">IWDFNamedPropertyStore</a>
 

 

