---
UID: NE:ntddsd.__unnamed_enum_4
title: SD_REQUEST_FUNCTION (ntddsd.h)
description: The SD_REQUEST_FUNCTION enumeration indicates the type of request packet that a Secure Digital (SD) card driver sends to the bus driver.
old-location: sd\sd_request_function.htm
tech.root: SD
ms.assetid: 9eec7597-be3a-4811-8786-11de0f9ac3da
ms.date: 02/15/2018
keywords: ["SD_REQUEST_FUNCTION enumeration"]
ms.keywords: SD.sd_request_function, SDRF_DEVICE_COMMAND, SDRF_GET_PROPERTY, SDRF_SET_PROPERTY, SD_REQUEST_FUNCTION, SD_REQUEST_FUNCTION enumeration [Buses], ntddsd/SDRF_DEVICE_COMMAND, ntddsd/SDRF_GET_PROPERTY, ntddsd/SDRF_SET_PROPERTY, ntddsd/SD_REQUEST_FUNCTION, sd-structs_db2d511c-e3e2-46e6-9d01-1723c1c8ec7f.xml
f1_keywords:
 - "ntddsd/SD_REQUEST_FUNCTION"
 - "SD_REQUEST_FUNCTION"
req.header: ntddsd.h
req.include-header: Ntddsd.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddsd.h
api_name:
- SD_REQUEST_FUNCTION
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# SD_REQUEST_FUNCTION enumeration


## -description


The SD_REQUEST_FUNCTION enumeration indicates the type of request packet that a Secure Digital (SD) card driver sends to the bus driver.


## -enum-fields




### -field SDRF_GET_PROPERTY

Indicates a get property request. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsd/ne-ntddsd-sdbus_property">SDBUS_PROPERTY</a> enumeration lists the properties that an SD driver can get or set.


### -field SDRF_SET_PROPERTY

Indicates a set property request. The SDBUS_PROPERTY enumeration lists the properties that an SD driver can get or set.


### -field SDRF_DEVICE_COMMAND

Indicates a device-specific command.


### -field SDRF_ERASE_COMMAND


### -field SDRF_MMC_SOFT_RESET


### -field SDRF_MMC_HPI




## -remarks



The caller of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequest">SdBusSubmitRequest</a> routine assigns a value from the SD_REQUEST_FUNCTION enumeration to the <b>RequestFunction</b> member of the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537931(v=vs.85)">SDBUS_REQUEST_PACKET</a> structure to specify the type of request.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537931(v=vs.85)">SDBUS_REQUEST_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequest">SdBusSubmitRequest</a>
 

 

