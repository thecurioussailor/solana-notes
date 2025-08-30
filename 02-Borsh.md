use borsh::{to_vec, BorshDeserialize, BorshSerialize};

#[derive(Debug, BorshDeserialize, BorshSerialize)]
struct User {
    name: String,
    age: u32,
    field: String
}
fn main() {
    let u = User {
        name: String::from("Harkirat"),
        age: 32,
        field: String::from("Computer Science"),
    };

    let bytes = to_vec(&u).unwrap();  //to_vec function comes from borsh that convert the struct into a vector of bytes
    let u2 = User::try_from_slice(&bytes).unwrap();
    println!("{:?}", bytes);
    println!("{:?}", u);
    println!("{:?}", u2);
}
