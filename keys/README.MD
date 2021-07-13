# CURL key deployment

## Getting Started

Make sure that the keys are stored in keys folder in the specified format.

Once your node is running, you will again notice that no blocks are being produced. At this point, you need to add your keys into the keystore. Remember you will need to complete these steps for each node in your network. You will add two types of keys for each node: Aura and GRANDPA keys. Aura keys are necessary for block production; GRANDPA keys are necessary for block finalization.

You can insert a key into the keystore by using curl from the command line. This approach may be preferable in a production setting, where you may be using a cloud-based virtual private server.

Because security is of the utmost concern in a production environment, it is important to take every precaution possible. In this case, that means taking care that you do not leave any traces of your keys behind, such as in your terminal's history. Create a file that you will use to define the body for your curl request:

```
{
  "jsonrpc":"2.0",
  "id":1,
  "method":"author_insertKey",
  "params": [
    "<aura/gran>",
    "<mnemonic phrase>",
    "<public key>"
  ]
}
```

## Best way for key deployment

Use the shell script "install-keys.sh" in this directory. Run the shell to deploy keys to each node.


### Run

Submit a new key via RPC, connect to where your `rpc-port` is listening

```sh
curl http://localhost:9933 -H "Content-Type:application/json;charset=utf-8" -d "@/path/to/file"

```
If you enter the command and parameters correctly, the node will return a JSON response as follows.
```sh
{ "jsonrpc": "2.0", "result": null, "id": 1 }

```
