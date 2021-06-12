---
UID: NN:ksproxy.IKsPropertySet
title: IKsPropertySet (ksproxy.h)
description: The IKsPropertySet interface provides methods that access properties of KS objects that are implemented in a KS minidriver.
tech.root: stream
ms.date: 06/11/2021
keywords: ["IKsPropertySet interface"]
ms.keywords: IKsPropertySet, IKsPropertySet interface [Streaming Media Devices], IKsPropertySet interface [Streaming Media Devices],described, dsound/IKsPropertySet, ksproxy_5f6316c6-5bcf-4155-b4a5-976a0cee8aa5.xml, stream.ikspropertyset
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
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
 - IKsPropertySet
 - ksproxy/IKsPropertySet
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dsound.h
api_name:
 - IKsPropertySet
---

# IKsPropertySet interface (ksproxy.h)

## -description

The **IKsPropertySet** interface provides methods that access properties of KS objects that are implemented in a KS minidriver.

The IID for this interface is IID_IKsPropertySet.

## -inheritance

The **IKsPropertySet** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

Header files *ksproxy.h* and *dsound.h* define similar but incompatible versions of the **IKsPropertySet** interface. Applications that require the KS proxy module should use the version defined in *ksproxy.h*. The DirectSound version of **IKsPropertySet** is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.

If an application must include both *ksproxy.h* and *dsound.h*, whichever header file the compiler scans first is the one whose definition of **IKsPropertySet** is used by the compiler.

The **IKsPropertySet** interface methods translate user-mode property requests into kernel-mode property sets that are used by KS minidrivers.

KS objects include, for example, KS filters, KS pins, and KS clocks.
