# Hashcash Proof of Work Algorithm

A __proof of work__ is a piece of data which is difficult (costly, time-consuming) to produce but easy for others to verify and which satisfies certain requirements. Producing a proof of work can be a random process with low probability so that a lot of trial and error is required on average before a valid proof of work is generated. Bitcoin uses the Hashcash proof of work system.

The algorithm is pretty simple: you must double hash (with SHA-256) a given `message` with a numeric `nonce` appended to it and find the nonce that creates a hexadecimal string with _n_ zeros at the beginning of it. The _n_ is called the difficulty.

For example, when you run the algorithm with the message `Hello, world!` and a difficulty of `3`, it gives you the nonce `4174`. Therefore, if you send the `message` and the `nonce` to anyone, he could easily verify that you expended a modest amount of CPU time calculating this nonce by double hashing the message plus the nonce, and expecting the first 3 digits of the __hexadecimal result__ to be zeros.

In Bitcoin, the algorithm is a little bit more complex and it is designed to increase or decrease the difficulty to force miners to take approximately 10 minutes before they find the nonce. If the miners take less than 10 minutes to find the nonce the difficulty increases.

## Deliverables

A ruby script that can run as a command line utility with the following inputs and outputs.

### Inputs

Input Name | Datatype | Example        | Description
---------- | -------- | -------------- | --------
message    | String   | Hello, world!  | The message to do the proof of work on
difficulty | Integer  | 3 (recommended) | The difficulty (number of zeros that the resulting hash must have)

### Outputs

Output Name | Datatype | Example
----------- | -------- | -------
PoW hash    | String [hex] | 0004b5ec0e58569b916cd0e55b1253e2da19e8cf4d291108f8146c0ad5bd3810
nonce      | Number   | 4174
Time spent  | Number [seconds] | 0.022134

## Example

```bash
$ ./pow "Hello, world\!" 3
Finished after 0.022134 Seconds
PoW Hash: 0004b5ec0e58569b916cd0e55b1253e2da19e8cf4d291108f8146c0ad5bd3810
Nonce used: 4174
```

## Notes

- We expect you to take no more than two hours on it.
- The code quality will be taken into account.
- We encourage you to communicate as much as you can, so please don’t be afraid of asking questions. Remember, there is no such thing as a dumb question!

**Good luck!!**
