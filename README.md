LineageOS
===========

Getting started
---------------

```
1. mkdir -p InFusionX-i9300 && cd InFusionX-i9300

2. Initialize your local repository using the LineageOS trees with a command
  repo init --depth=1 -u git://github.com/LineageOS/android.git -b lineage-16.0
  
3. Clone this repo:
  git clone https://github.com/team-infusion-developers/android_local_manifests_i9300 .repo/local_manifests -b opt-cm-16.0

4. Sync LineageOS trees:
  repo sync --no-tags --no-clone-bundle --force-sync -c -j8

5. Generate the keys used for ROM signing:

From the root of your Android tree, run these commands, altering the subject line to reflect your information:

subject='/C=US/ST=California/L=Mountain View/O=Android/OU=Android/CN=Android/emailAddress=android@android.com'
mkdir .android-certs
for x in releasekey platform shared media testkey; do \
    ./development/tools/make_key .android-certs/$x "$subject"; \
done

6. To build:
  . build/envsetup.sh
  lunch lineage_i9300-userdebug
  make -j8 bacon
```
