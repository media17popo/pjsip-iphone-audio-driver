An audio driver that connects the PJSIP framework to the iPhone audio system, using the supplied Voice Processing I/O AudioUnit.

**Benefits of using the Voice Processing I/O AudioUnit:**
  * Very low-latency
  * Connects to input and output hardware
  * Performs sample rate conversions between the hardware and your application
  * Provides acoustic echo cancellation for two-way chat
    * Does not use pjsip echo cancellation!
