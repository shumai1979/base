// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

// Este é o contrato simples que será "clonado"
contract SimpleContract {
    address public owner;
    constructor(address _owner) {
        owner = _owner;
    }
}

// Esta é a sua Fábrica
contract ContractFactory {
    address[] public deployedContracts;

    function createNewContract() public {
        // O seu endereço (msg.sender) gera um novo contrato na rede
        SimpleContract newContract = new SimpleContract(msg.sender);
        deployedContracts.push(address(newContract));
    }

    function getCount() public view returns (uint256) {
        return deployedContracts.length;
    }
}

contrato 1: 0x9e3e0cd92ea976faefce00f66c459033fea81e81
