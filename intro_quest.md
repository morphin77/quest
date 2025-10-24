[Back](README.md)
```rust
use std::io;

fn split_number_tuple(num: u8) -> Result<(u8, u8), String> {
    if !(10..=99).contains(&num) {
        return Err("Число должно быть от 10 до 99".to_string());
    }
    Ok((num / 10, num % 10))
}

fn main() {
    let mut input = String::new();

    io::stdin()
        .read_line(&mut input)
        .expect("Ошибка чтения строки");

    let age = input.trim().parse::<u8>().unwrap();
    let a: f32 = split_number_tuple(age).unwrap().0 as f32;
    let b: f32 = split_number_tuple(age).unwrap().1 as f32;
    println!("{}", a*a + a/b);
}

```