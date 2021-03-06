---
title: "ICorRuntimeHost::SwitchInLogicalThreadState Method"
ms.date: "03/30/2017"
api_name: 
  - "ICorRuntimeHost.SwitchInLogicalThreadState"
api_location: 
  - "mscoree.dll"
api_type: 
  - "COM"
f1_keywords: 
  - "ICorRuntimeHost::SwitchInLogicalThreadState"
helpviewer_keywords: 
  - "ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]"
  - "SwitchInLogicalThreadState method [.NET Framework hosting]"
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type: 
  - "apiref"
author: "rpetrusha"
ms.author: "ronpet"
---
# ICorRuntimeHost::SwitchInLogicalThreadState Method
This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.  
  
## Syntax  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## Parameters  
 `pFiberCookie`  
 [in] Cookie that indicates the fiber to use.  
  
## Requirements  
 **Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Library:** Included as a resource in MSCorEE.dll  
  
 **.NET Framework Version:** 1.0, 1.1  
  
## See also
- [ICorRuntimeHost Interface](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
