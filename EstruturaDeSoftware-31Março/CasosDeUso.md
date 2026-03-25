# Casos de Uso - Sistema de Gerenciamento de Incidentes

**Aluno:** Caio Caramés Lanzelotti da Silva  
**RA:** 10308718

**Aluno:** Gabriel Bello  
**RA:** 10416808

**Aluno:** Nicolas Guilherme Da Silva  
**RA:** 10322847

**Aluno:** Gabriel Nobrega Neri  
**RA:** 10419208

**Aluno:** Rafael Riki Nascimento de Oliveira  
**RA:** 10418331


## Descrição dos Casos de Uso
### UC001 - Registrar Incidente
O analista registra um novo incidente no sistema, incluindo informações iniciais como descrição, data, ativos afetados e envolvidos.

### UC002 - Classificar Incidente
O incidente é classificado de acordo com nível de risco e sigilo, garantindo tratamento adequado.

### UC003 - Anexar Evidências
Permite adicionar logs, arquivos e outras evidências relacionadas ao incidente.

### UC004 - Atualizar Status do Incidente
O analista atualiza o progresso do incidente (aberto, em análise, resolvido).

### UC005 - Atribuir Responsável
O administrador designa um responsável pelo tratamento do incidente.

### UC006 - Monitorar Incidente
Permite acompanhar a evolução e ações realizadas no incidente.

### UC007 - Avaliar Relatório
O comitê analisa o relatório final do incidente, incluindo riscos e ações tomadas.

### UC008 - Aprovar Encerramento
O comitê aprova ou rejeita o encerramento do incidente.

### UC009 - Verificar Conformidade LGPD
O DPO verifica se o tratamento do incidente está em conformidade com a LGPD.

---

## Diagrama de Casos de Uso

```plantuml
@startuml
left to right direction

actor "Analista de Segurança" as Analista
actor "Administrador de Rede" as Admin
actor "Comitê de Segurança" as Comitê
actor "DPO" as DPO

rectangle Sistema {

    Analista -- (UC001 - Registrar Incidente)
    Analista -- (UC002 - Classificar Incidente)
    Analista -- (UC003 - Anexar Evidências)
    Analista -- (UC004 - Atualizar Status do Incidente)

    Admin -- (UC005 - Atribuir Responsável)
    Admin -- (UC006 - Monitorar Incidente)

    Comitê -- (UC007 - Avaliar Relatório)
    Comitê -- (UC008 - Aprovar Encerramento)

    DPO -- (UC009 - Verificar Conformidade LGPD)

    (UC001 - Registrar Incidente) --> (UC002 - Classificar Incidente)
    (UC001 - Registrar Incidente) --> (UC003 - Anexar Evidências)
    (UC004 - Atualizar Status do Incidente) --> (UC006 - Monitorar Incidente)
    (UC006 - Monitorar Incidente) --> (UC007 - Avaliar Relatório)
    (UC007 - Avaliar Relatório) --> (UC008 - Aprovar Encerramento)

}

@enduml