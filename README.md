# boinc-rpc-rust
Rust API for BOINC client.

## Usage example
```
extern crate boinc_rpc as rpc;

fn main() {
    let client = rpc::SimpleClient::default();
    client.host = std::net::SocketAddr::new(std::net::IpAddr::V4(std::net::Ipv4Addr::new(127, 0, 0, 1)), 31416);
    client.password = Some("my-pass-in-gui_rpc_auth.cfg".into());

    println!("{:?}\n", client.get_messages(0));
    println!("{:?}\n", client.get_projects());
    println!("{:?}\n", client.get_account_manager_info());
    println!("{:?}\n", client.exchange_versions(&rpc::models::VersionInfo::default()));
    println!("{:?}\n", client.get_results(false));
}
```

## License
This program is free software: you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.