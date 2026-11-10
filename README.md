# revisao-sistema-equipamentos

class Equipamento: 
    def init(self, codigo, nome, quantidade): 
        self.codigo = codigo 
        self.nome = nome 
        self.quantidade = quantidade 
estoque = [] 
def cadastrar_equipamento(codigo, nome, quantidade): 
    equipamento = Equipamento(codigo, nome, quantidade) 
    estoque.append(equipamento) 
def emprestar_equipamento(codigo): 
    for equipamento in estoque: 
        if equipamento.codigo == codigo: 
            if equipamento.quantidade > 0: 
                equipamento.quantidade -= 1 
                return True 
    return False 
def devolver_equipamento(codigo): 
    for equipamento in estoque: 
        if equipamento.codigo == codigo: 
            equipamento.quantidade += 1 
            return True 
    return False 
def consultar_quantidade(codigo): 
    for equipamento in estoque: 
        if equipamento.codigo == codigo: 
            return equipamento.quantidade 
    return None
