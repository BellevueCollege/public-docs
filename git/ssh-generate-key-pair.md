# Generate a SSH Key Pair for Authentication

SSH is the recommended protocol for exchanging commits with a git host. This
document explains how to generate a key pair for use with authenticating to git
hosts that support the SSH protocol.

**NOTE:** This process generally only needs to be completed once. You may reuse
your generated public key with multiple systems. Advanced users may wish to use
separate key pairs for different systems (see
[Using Different Key Pairs for Different Hosts]
(#using-different-key-pairs-for-different-hosts) below).

## Generating the Key Pair

From the command prompt run the following **ssh-keygen** command to have your
system generate a new key RSA pair in your **.ssh/** directory.

```
ssh-keygen -b 4096 -t rsa
```

After running this command you will be prompted to enter a file path to use for
saving your key. You should hit enter to use the default file path.

```
Enter file in which to save the key (/home/CAMPUS/jwindle/.ssh/id_rsa):
```

Finally you will be prompted for a passphrase which is optional. If you decide
to enter a passphrase it will be used to encrypt your private key so that no one
can use it without knowing your passphrase.

Unless you have an ssh-agent setup you will also be prompted for your passphrase
each time you use your private key to interact with a git repository host over
SSH, which can be annoying.

For security purposes it is considered best practice to set a passphrase for
your private key.

```
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

When you are done setting your passphrase **ssh-keygen** will then output some
additional information about your newly generated key pair. Don't worry to much
about this additional information as it is not often used and can be displayed
again (if needed) at a later date.

## Using Your Key Pair

You should now have two new files in your **.ssh/** directory, **id_rsa** and
**id_rsa.pub**

The **id_rsa** file contains your private key. Your private key is like a
password and should never be needed by anyone else but yourself.
**DO NOT SHARE THIS FILE**.

The **id_rsa.pub** file contains your public key and will need to be installed
on the SSH enabled git repository host. Feel free to copy and send out the
contents of this file as needed and/or requested.

These files can also be transferred to **.ssh/** folders of other computers and
operating system platforms. It is however a security best practice to generate
a unique key pair for each system that you authenticate from.

## Using Different Key Pairs for Different Hosts

**TODO:** Write this section.
