# H5Radar — Health Radar for Modern Engineering Teams

**H5Radar** is an open-source platform for documenting and visualizing your organization's technology stack in a structured and consistent way.

It provides a clear view of technologies used across projects and teams, allowing you to track maturity, categorize technologies by domain, and analyze license compliance.

## Key features

- A technology catalog where each technology is classified by:
    - **Domain** (e.g. Languages, Infrastructure, Datastores, Data Management|Tools)
    - **Maturity** (e.g. Adopt, Trial, Assess, Hold)
- Visualization of selected technologies as an interactive radar chart
- License tracking with compliance levels (e.g. approved, restricted, prohibited)
- Pie chart visualization for license risk analysis

## Repository overview

| Repository                                   | Description                                                  |
|----------------------------------------------|--------------------------------------------------------------|
| [`docs`](https://github.com/h5radar/docs)              | Documentation and user guides                                |
| [`ansible`](https://github.com/h5radar/ansible)        | Installer and provisioning scripts for H5Radar deployment     |
| [`app-ui`](https://github.com/h5radar/app-ui)          | Web interface for radar and license visualization             |
| [`account`](https://github.com/h5radar/account)        | Authentication and user management (in progress)              |
| [`radar`](https://github.com/h5radar/radar)            | Base catalog of technologies with metadata                    |

## Installation

H5Radar supports multiple installation modes: from prebuilt binaries and from source code.

The simplest and recommended way is to install from prebuilt binaries using the Ansible installer provided in the [`ansible`](https://github.com/h5radar/ansible) repository.

The basic steps for this mode are:

1. Clone the Ansible installer repository from the [`ansible`](https://github.com/h5radar/ansible) repository
2. Copy the `inventory/development` directory to `inventory/production`
3. Edit the `hosts` file inside the inventory to specify the IP address of your target virtual machine
4. Configure installation parameters such as:
    - SSL certificate type (self-signed, Let's Encrypt, or external certificates)
    - Reverse proxy choice (Nginx or Apache)
    - Other relevant parameters
5. Run the Ansible playbook installer with the command:
   ```bash
   ansible-playbook -v --diff --inventory inventory/production main.yml
   ```

This installation process sets up all required components, including the web UI and backend services.

All installation methods, including installation from prebuilt binaries and building from source, are documented in detail in the [official documentation](https://docs.h5radar.com/).

## Roadmap

Planned features under active discussion:

- Source code analysis for unapproved technologies
- CI/CD integration for radar policy checks
- Extended API and multi-project dashboards

Discussions about the roadmap take place centrally at the organization’s [discussions](https://github.com/orgs/h5radar/discussions) forum on GitHub.

## Who is it for

- Engineering teams managing complex or regulated tech environments
- Architects aiming to introduce transparent tech governance
- Platform and DevOps teams interested in license and stack compliance

## Contributing

We welcome contributions from the community:

- Submit issues or pull requests to relevant repositories
- Participate in roadmap discussions
- Share real-world use cases or feature ideas

For questions or contributions, please start a thread in our [Discussions](https://github.com/orgs/h5radar/discussions).

## License

H5Radar is open-source and licensed under the MIT License.
