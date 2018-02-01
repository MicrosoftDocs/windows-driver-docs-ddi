---
UID: NF:drmk.DrmAddContentHandlers
title: DrmAddContentHandlers function
author: windows-driver-content
description: The DrmAddContentHandlers function provides the system with a list of functions that handle protected content.
old-location: audio\drmaddcontenthandlers.htm
old-project: audio
ms.assetid: da2ec371-052a-4ea1-9336-9e32df936227
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.drmaddcontenthandlers, DrmAddContentHandlers, drmk/DrmAddContentHandlers, aud-prop2_94f530fb-9766-4d61-a002-b1c7bd5183d5.xml, DrmAddContentHandlers function [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Universal
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
req.lib: Drmk.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Drmk.lib
-	Drmk.dll
apiname:
-	DrmAddContentHandlers
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# DrmAddContentHandlers function


## -description


The <code>DrmAddContentHandlers</code> function provides the system with a list of functions that handle protected content.


## -syntax


````
NTSTATUS DrmAddContentHandlers(
  _In_ ULONG ContentId,
  _In_ PVOID *paHandlers,
  _In_ ULONG NumHandlers
);
````


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param paHandlers [in]

Pointer to an array of function pointers. Each array element points to a content handler.


### -param NumHandlers [in]

Specifies the number of function pointers in the <i>paHandlers</i> array.


## -returns


<code>DrmAddContentHandlers</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


Before allowing protected content to flow through a data path, the system verifies that the data path is secure. To do so, the system authenticates each module in the data path beginning at the upstream end of the data path and moving downstream. As each module is authenticated, that module gives the system information about the next module in the data path so that it can also be authenticated. To be successfully authenticated, a module's binary file must be signed as DRM-compliant.

If two adjacent modules communicate with each other through either the <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> function or the downstream module's COM interface, the upstream module calls the <a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a> or <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function, respectively, to provide the system with information about the downstream module. However, if the two modules use any other type of interface to communicate, the upstream module calls the <code>DrmAddContentHandlers</code> function instead.

The <i>paHandlers</i> array contains function pointers to entry points in the downstream module. <code>DrmAddContentHandlers</code> authenticates the module that implements these functions. (If the entry points are distributed among several modules, the function authenticates all these modules.) The vendor-defined functions in this array make up an interface that is understood by both the module that calls the functions and the module that implements the functions. <code>DrmAddContentHandlers</code> does not directly call any of these functions.

The upstream module can pass both the content ID and content rights to the downstream module by using one of the functions in the <i>paHandlers</i> array for this purpose. The downstream module needs the content ID to advise the system of any modules to which it sends the protected content.

<i>DrmAddContentHandlers</i> performs the same function as <a href="..\portcls\nf-portcls-pcaddcontenthandlers.md">PcAddContentHandlers</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536575">IDrmPort2::AddContentHandlers</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.



## -see-also

<a href="..\portcls\nf-portcls-pcaddcontenthandlers.md">PcAddContentHandlers</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536575">IDrmPort2::AddContentHandlers</a>

<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DrmAddContentHandlers function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

