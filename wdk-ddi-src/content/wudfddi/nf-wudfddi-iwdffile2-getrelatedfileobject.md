---
UID: NF:wudfddi.IWDFFile2.GetRelatedFileObject
title: IWDFFile2::GetRelatedFileObject (wudfddi.h)
description: The GetRelatedFileObject method retrieves the IWDFFile interface of a related file object, which is a file object that has a technology-specific relationship with another file object.
old-location: wdf\iwdffile2_getrelatedfileobject.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFFile2::GetRelatedFileObject"]
ms.keywords: GetRelatedFileObject, GetRelatedFileObject method, GetRelatedFileObject method,IWDFFile2 interface, IWDFFile2 interface,GetRelatedFileObject method, IWDFFile2.GetRelatedFileObject, IWDFFile2::GetRelatedFileObject, UMDFFileObjectRef_f65433dc-ba63-456e-beff-ef7c9e2dffa8.xml, umdf.iwdffile2_getrelatedfileobject, wdf.iwdffile2_getrelatedfileobject, wudfddi/IWDFFile2::GetRelatedFileObject
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFFile2::GetRelatedFileObject
 - wudfddi/IWDFFile2::GetRelatedFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFFile2.GetRelatedFileObject
---

# IWDFFile2::GetRelatedFileObject


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetRelatedFileObject</b> method retrieves the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface of a <i>related file object</i>, which is a file object that has a technology-specific relationship with another file object.

## -parameters

### -param ppRelatedFileObj 

[out]
The address of a location that receives a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface of a UMDF file object. This file object is related to the file object that exposes the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile2">IWDFFile2</a> interface's parent <b>IWDFFile</b> interface.

## -remarks

Use of related file objects is technology-specific. For example, <a href="/windows-hardware/drivers/stream/kernel-streaming">kernel streaming</a> uses related file objects to represent the parent filters of child pins.

For more information about related file objects, see the <b>GetRelatedFileObject</b> member of the kernel-mode <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure.


#### Examples

The following code example retrieves the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface of a related file object, from the <b>IWDFFile</b> interface that a driver's <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackcreate-oncreatefile">IQueueCallbackCreate::OnCreateFile</a>  callback function receives.


```
VOID
STDMETHODCALLTYPE
CMyQueue::OnCreateFile(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in IWDFFile*  pWdfFileObject
    )
 ...
    IWDFFile*  pWdfRelatedFileObject = NULL;
    IWDFFile2*  pWdfFileObject2 = NULL;
    HRESULT  hr = S_OK;

    //
    // Obtain IWDFFile2 interface from IWDFFile.
    //
    hr = pWdfFileObject->QueryInterface(IID_PPV_ARGS(&pWdfFileObject2));
    if (!SUCCEEDED(hr))
    {
        goto Done;
    }
    pWdfFileObject2->GetRelatedFileObject(&pWdfRelatedFileObject);
    ...
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile2">IWDFFile2</a>
