---
UID: NS:mpiowmi._DSM_VERSION
title: "_DSM_VERSION"
author: windows-driver-content
description: The DSM_VERSION structure represents version information that is associated with a DSM binary or package.
old-location: storage\dsm_version.htm
tech.root: storage
ms.assetid: 1aa264fa-b552-41a0-bd43-a62f8f2b533b
ms.date: 03/29/2018
ms.keywords: "*PDSM_VERSION, DSM_VERSION, DSM_VERSION structure [Storage Devices], PDSM_VERSION, PDSM_VERSION structure pointer [Storage Devices], _DSM_VERSION, mpiowmi/DSM_VERSION, mpiowmi/PDSM_VERSION, storage.dsm_version, structs-scsibus_3e00c2b2-0497-4aab-b2e0-a6a5d998e560.xml"
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mpiowmi.h
api_name:
-	DSM_VERSION
product:
- Windows
targetos: Windows
req.typenames: DSM_VERSION, *PDSM_VERSION
---

# _DSM_VERSION structure


## -description


The DSM_VERSION structure represents version information that is associated with a DSM binary or package. While this assumes that a DSM's version will be of the type MajorVersion.MinorVersion.ProductBuild.QfeNumber, it is not mandatory for the DSM to follow this convention. The DSM must, however, fill in zeros for the fields its does not support.


## -struct-fields




### -field MajorVersion

An unsigned 32-bitfield that represents the major version portion of the version.


### -field MinorVersion

An unsigned 32-bitfield that represents the minor version portion of the version.


### -field ProductBuild

An unsigned 32-bitfield that represents the product build portion of the version.


### -field QfeNumber

An unsigned 32-bitfield that represents the QFE number portion of the version.

