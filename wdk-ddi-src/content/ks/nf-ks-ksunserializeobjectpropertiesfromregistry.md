---
UID: NF:ks.KsUnserializeObjectPropertiesFromRegistry
title: KsUnserializeObjectPropertiesFromRegistry function
author: windows-driver-content
description: The KsUnserializeObjectPropertiesFromRegistry function, when given a destination object and a registry path, enumerates the named values and applies them as serialized data to the specified property sets listed in the serialized data.
old-location: stream\ksunserializeobjectpropertiesfromregistry.htm
old-project: stream
ms.assetid: e08ddef7-5942-4943-9dbe-9658279892f0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsUnserializeObjectPropertiesFromRegistry, KsUnserializeObjectPropertiesFromRegistry function [Streaming Media Devices], ks/KsUnserializeObjectPropertiesFromRegistry, ksfunc_09710ce5-9236-47cc-84b2-4ced36aa654b.xml, stream.ksunserializeobjectpropertiesfromregistry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsUnserializeObjectPropertiesFromRegistry
product: Windows
targetos: Windows
req.typenames: 
---

# KsUnserializeObjectPropertiesFromRegistry function


## -description


The <b>KsUnserializeObjectPropertiesFromRegistry</b> function, when given a destination object and a registry path, enumerates the named values and applies them as serialized data to the specified property sets listed in the serialized data. An IRP is generated when sending the serialized data, so no assumption is made on use of KS property structures to internally define the property sets. The function does not use the names of the values.


## -syntax


````
NTSTATUS KsUnserializeObjectPropertiesFromRegistry(
  _In_     PFILE_OBJECT    FileObject ,
  _In_opt_ HANDLE          ParentKey ,
  _In_opt_ PUNICODE_STRING RegistryPath 
);
````


## -parameters




### -param FileObject [in]

Specifies the file object whose properties are being set.


### -param ParentKey [in, optional]

Optionally contains a handle to the parent of the path, or <b>NULL</b>. The Parent Key and/or the <i>RegistryPath</i> must be passed.


### -param RegistryPath [in, optional]

Optionally contains the path to the key whose subkeys will be enumerated as property sets, or otherwise <b>NULL</b>. The <i>ParentKey</i> and/or the Registry Path must be passed.


## -returns



The <b>KsUnserializeObjectPropertiesFromRegistry</b> function returns STATUS_SUCCESS if the property sets were unserialized. The function returns an error if the registry path was invalid, one of the subkeys was invalid, setting a property was unsuccessful, the serialized format was invalid, or a property set was not supported on the object. 



