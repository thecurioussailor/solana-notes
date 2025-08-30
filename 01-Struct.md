#[derive(Debug)]
struct User {
    name: String,
    age: u32,
}
fn main() {
    let u = User {
        name: String::from("Harkirat"),
        age: 32
    };

    println!("{:?}", u);
}
