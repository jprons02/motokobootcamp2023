1) Who controls the ledger canister?
The NNS subnet

2) What is the subnet of the canister with the id: mwrha-maaaa-aaaab-qabqq-cai? How many nodes are running this subnet?
There is no subnet.
Controllers: a3hwk-dyaaa-aaaab-qaa4a-cai k3f6a-5uxhv-dqjj6-762lc-yazgp-drpws-a35e7-wf27k-ujuio-ye2lh-xqe
Module hash: 0xd8d65e5ebdf7f884e59bdf73061c16f8186dcab128272343a047b59098f7cc93

3) I have a neuron with 1O ICPs locked with a dissolve delay of 4 years - my neuron has been locked for 2 years. What is my expected voting power?
5.99 

4) What is wrong with the following code?
actor {
  let n : Nat = 50;
  let t : Text = "Hello";

  public func convert_to_text(m : Nat) : async Text {
    Nat.toText(m);
  };
}
You need to import Nat. Correct code: 
import Nat "mo:base/Nat"
actor {
  let n : Nat = 50;
  let t : Text = "Hello";

  public func convert_to_text(m : Nat) : async Text {
    Nat.toText(m);
  };
}


5) What is wrong with the following code?
actor {
  var languages : [var Text] = ["English", "German", "Chinese", "Japanese", "French"];

  public func show_languages(language : Text) : async [var Text] {
    return (languages);
  };
}
Need to delete "var" from inside array type declaration. Correct code:  
actor {
  var languages : [Text] = ["English", "German", "Chinese", "Japanese", "French"];

  public func show_languages(language : Text) : async [Text] {
    return (languages);
  };
}


6) What is wrong with the following code?
actor {
  var languages : [Text] = ["English", "German", "Chinese", "Japanese", "French"];

  public func add_language(new_language: Text) : async [Text] {
    languages := Array.append<Text>(languages, [new_language]);
    return (languages);
  }; 
}
Need to import Array. Correct code: 
import Array "mo:base/Array"
actor {
  var languages : [Text] = ["English", "German", "Chinese", "Japanese", "French"];

  public func add_language(new_language: Text) : async [Text] {
    languages := Array.append<Text>(languages, [new_language]);
    return (languages);
  }; 
}