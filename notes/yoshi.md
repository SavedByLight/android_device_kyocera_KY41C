```
## Finding decrypt functions...
In libkeymaster_portable.so implemented as:
```
keymaster::EcKeyFactory::CreateEmptyKey(keymaster::AuthorizationSet&&, keymaster::AuthorizationSet&&, keymaster::UniquePtr<keymaster::AsymmetricKey, keymaster::DefaultDelete<keymaster::AsymmetricKey>>*) const
```
libsoftkeymasterdevice.so wants:
```
keymaster::EcKeyFactory::CreateEmptyKey(keymaster::AuthorizationSet&&, keymaster::AuthorizationSet&&, std::__1::unique_ptr<keymaster::AsymmetricKey, std::__1::default_delete<keymaster::AsymmetricKey>>*) const
```
A classic implementation back in 2015 used to be in ec_key.cpp:
```
keymaster_error_t EcKeyFactory::CreateEmptyKey(const AuthorizationSet& hw_enforced,
                                               const AuthorizationSet& sw_enforced,
                                               UniquePtr<AsymmetricKey>* key)
```
