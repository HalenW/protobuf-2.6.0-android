# protobuf-2.x.x android


Google protobuf for Android NDK

Only use versions below protobuf 3.0.0

## complie
To compile other versions, you only need to copy the entire google/protobuf directory to the src/main/jni directory

###
issue:undefined reference to `typeinfo for google::protobuf::Message'
you need to turn on RTTI support. 
https://developer.android.com/ndk/guides/cpp-support#rtti

To enable RTTI across your whole application in ndk-build, add the following line to your `Application.mk` file:

`
APP_CPPFLAGS := -frtti
`

To enable RTTI for a single ndk-build module, add the following line to the given module in its `Android.mk`:

`
LOCAL_CPP_FEATURES := rtti
`
Alternatively, you can use:

`
LOCAL_CPPFLAGS := -frtti
`
